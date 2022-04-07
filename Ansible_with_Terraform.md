
If you are just using the local-exec provider in some cases the local-exec provisioner starts without waiting for an instance to launch so, it will fail because by the time it will try to connect there is nobody listening. Error attached below,

```
Error: local-exec provisioner error
fatal: [3.85.7.229]: UNREACHABLE! => {"changed": false, "msg": "Failed to connect to the host via ssh: Host key verification failed.", "unreachable": true}
```
