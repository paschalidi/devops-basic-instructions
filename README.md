# devops-simple-commands
This Repository is a collection of Implementation documents. 

### Purpose:
By following this repository you can able to setup a DevOps CI/CD Pipeline using
- git
- Jenkins
- Maven
- Ansible
- Docker &
- Kubernetes

# Linux 

Find log errors
```
grep -ni 'error\|failure' $(sudo find /var/log -name cfn\* -or -name cloud-init\*)
```
