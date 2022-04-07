## How to run Ansible without specifying the inventory but the host directly using ansible-palybook flags?  
Surprisingly, the trick is to append a ,
The host parameter preceding the , can be either a hostname or an IPv4/v6 address.
```
ansible-playbook -i example.com, playbook.yml   # Requires 'hosts: all' in the playbook  
ansible-playbook -u ec2-user -i 93.184.216.119, --private-key aws.pem ansible_excel.yaml  
```

Sample ansible code to create user

```
---
- name: monitor user creation
  hosts: all
  gather_facts: no
  become_user: root
  become: yes
  tasks:
    - name: monitor exists with UID 4000
      user:
        name: monitor
        uid: 4000
        state: present
```

If you are just using the local-exec provider to call the ansible-playbook command the provider may fail in most cases as the local-exec provisioner starts without waiting for an instance to launch. Because by the time it will try to connect there is nobody to listen. Error attached below,

```
Error: local-exec provisioner error
fatal: [3.85.7.229]: UNREACHABLE! => {"changed": false, "msg": "Failed to connect to the host via ssh: Host key verification failed.", "unreachable": true}
```
To avoid this you can use the local-exec provider along with the remot-exec provider as mentioned below

```
provisioner "remote-exec" {
    inline = ["sudo dnf -y install python"]

    connection {
      type        = "ssh"
      user        = "ec2-user"
      private_key = "${file(var.ssh_key_private)}"
    }
  }

  provisioner "local-exec" {
    command = "ansible-playbook -u ec2-user -i '${self.public_ip},' --private-key ${var.ssh_key_private} provision.yml" 
  }
  ```
  
