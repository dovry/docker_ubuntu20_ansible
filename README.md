# Docker Ubuntu 20.04 Ansible

![Build Status](https://github.com/dovry/docker_ubuntu20_ansible/workflows/Basic%20build%20and%20push%20to%20Docker%20hub/badge.svg)

![Docker Pulls](https://img.shields.io/docker/pulls/dovry/docker_ubuntu20_ansible)

Test Ansible roles in an Ubuntu 20.04 container

## How to use the container

```yaml
docker run --rm -d -it \
--name ubuntu20_ansible \
-v /sys/fs/cgroup:/sys/fs/cgroup:ro \
-v /run/lock:/run/lock:ro \
-v /etc/ansible:/etc/ansible:ro \
dovry/docker_ubuntu20_ansible
```

And then either exec into the container and start hacking away with:

`docker exec -it ubuntu20_ansible /bin/bash`

or execute a role directly with a command such as this:

`docker exec -it ubuntu20_ansible ansible-playbook /etc/ansible/playbooks/test-role.yml`

Remember to set the target host in the playbook so that it is run in the container

`hosts: localhost`
