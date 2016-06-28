Ansible-Test
============

A repository to deploy a flask application to a vagrant machine.
Ansible playbook manages all the process.

You need to have git, ansible and vagrant with VirtualBox provider installed on your host machine

You may get the repository from github and deploy vagrant:

```
$ git clone https://github.com/koksay/ansible-test.git ansible-test-project

$ cd ansible-test-project

$ vagrant up

$ ansible-playbook deploy_flask.yml
```

