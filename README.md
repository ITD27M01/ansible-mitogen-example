# Check mitogen inside collection

1. Install python requirements:

```shell
$ pip3 install -r requirements.txt
```

2. Install ansible requirements:

```shell
$ ansible-galaxy install -r requirements.yml
```

3. Check:

```shell
(base) > ansible-doc -t strategy -l
debug                                Executes tasks in interactive debug session                   
free                                 Executes tasks without waiting for all hosts
host_pinned                          Executes tasks on each host without interruption
itd27m01.example.mitogen             Executes tasks in a linear fashion
itd27m01.example.mitogen_free        UNDOCUMENTED
itd27m01.example.mitogen_host_pinned UNDOCUMENTED
itd27m01.example.mitogen_linear      UNDOCUMENTED
linear                               Executes tasks in a linear fashion
```

```shell
(base) > ansible-playbook site.yml

PLAY [Check strategy plugin] ******************************************************************************

TASK [Gathering Facts] ************************************************************************************
ok: [localhost]

TASK [ping] ***********************************************************************************************
ok: [localhost]

PLAY RECAP ************************************************************************************************
localhost             : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0  ignored=0
```

```shell
(base) > ansible --version
ansible [core 2.11.12] 
  config file = /Users/me/src/ansible-mitogen-example/ansible.cfg
  configured module search path = ['/Users/me/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /Users/me/opt/anaconda3/envs/ansible-mitogen-example/lib/python3.10/site-packages/ansible
  ansible collection location = /Users/me/src/ansible-mitogen-example
  executable location = /Users/me/opt/anaconda3/envs/ansible-mitogen-example/bin/ansible
  python version = 3.10.4 (main, Mar 31 2022, 03:37:37) [Clang 12.0.0 ]
  jinja version = 3.1.2
  libyaml = True
```