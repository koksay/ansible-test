Ansible-Test
============

A repository to deploy a flask application to a vagrant machine.
Ansible playbook manages all the process.

You need to have [git](https://git-scm.com/downloads), [ansible](http://docs.ansible.com/ansible/intro_installation.html), [vagrant](https://www.vagrantup.com/downloads.html) and [VirtualBox](https://www.virtualbox.org/wiki/Downloads)  installed on your host machine

You may get the repository from github and deploy vagrant:

```
$ git clone https://github.com/koksay/ansible-test.git ansible-test-project

$ cd ansible-test-project

$ vagrant up --provider=virtualbox

$ ansible-playbook deploy_flask.yml
```

If everything went well, you should see below output from ansible:

```
PLAY [Deploy flask on gunicorn] ************************************************

TASK [setup] *******************************************************************
ok: [flaskapp01]

TASK [install apt packages] ****************************************************
changed: [flaskapp01] => (item=[u'git', u'nginx', u'python-dev', u'python-pip', u'python-setuptools', u'python-virtualenv', u'supervisor'])

TASK [check out the flask application repository] ******************************
changed: [flaskapp01]

TASK [install required python packages] ****************************************
changed: [flaskapp01] => (item=gunicorn)
changed: [flaskapp01] => (item=Flask)

TASK [set the gunicorn config file] ********************************************
changed: [flaskapp01]

TASK [set the supervisor config file] ******************************************
changed: [flaskapp01]

TASK [set the nginx config file] ***********************************************
changed: [flaskapp01]

TASK [enable the nginx config file] ********************************************
changed: [flaskapp01]

TASK [remove the default nginx config file] ************************************
changed: [flaskapp01]

TASK [ensure config path exists] ***********************************************
changed: [flaskapp01]

TASK [create ssl certificates] *************************************************
changed: [flaskapp01]

RUNNING HANDLER [restart supervisord] ******************************************
changed: [flaskapp01]

RUNNING HANDLER [restart nginx] ************************************************
changed: [flaskapp01]

PLAY RECAP *********************************************************************
flaskapp01                 : ok=13   changed=12   unreachable=0    failed=0   
```

Now you can reach the flask application from below address:


http://192.168.1.10.xip.io


You may find the flask codes below:

```
$ vagrant ssh

$ cd ~/flask_app/project
```

