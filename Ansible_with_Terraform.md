
If you are just using the local-exec provider to call the ansible-playbook command the provider may fail in most cases as the local-exec provisioner starts without waiting for an instance to launch. Because by the time it will try to connect there is nobody listening. Error attached below,

```
Error: local-exec provisioner error
fatal: [3.85.7.229]: UNREACHABLE! => {"changed": false, "msg": "Failed to connect to the host via ssh: Host key verification failed.", "unreachable": true}
```
