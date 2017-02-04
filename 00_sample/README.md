
在本目录下，执行下面的命令来查看测试结果:

```
ansible-playbook site*.yml
```
----------

请参考输出的结果:
```
ansible-playbook site.yml
```
结果为：
```
[jshi@jjshi 01_call_simple_role]$ ansible-playbook site.yml

PLAY [all] *********************************************************************

TASK [setup] *******************************************************************
ok: [localhost]

TASK [simple : Task in role demo] **********************************************
ok: [localhost] => {
    "msg": "This is very simplest role without any variable"
}

TASK [Tasks in site.yml] *******************************************************
ok: [localhost] => {
    "msg": "This is a task in site.yml"
}

PLAY RECAP *********************************************************************
localhost                  : ok=3    changed=0    unreachable=0    failed=0    

```
----------
```
ansible-playbook site_with_pre_and_post.yml
```
执行结果为：
```
[jshi@jjshi 01_call_simple_role]$ ansible-playbook site_with_pre_and_post.yml

PLAY [all] *********************************************************************

TASK [setup] *******************************************************************
ok: [localhost]

TASK [pre task] ****************************************************************
changed: [localhost]

TASK [simple : Task in role demo] **********************************************
ok: [localhost] => {
    "msg": "This is very simplest role without any variable"
}

TASK [Tasks in site*.yml] ******************************************************
ok: [localhost] => {
    "msg": "This is a task in site*.yml"
}

TASK [post task] ***************************************************************
changed: [localhost]

PLAY RECAP *********************************************************************
localhost                  : ok=5    changed=2    unreachable=0    failed=0   
```
----------
```
ansible-playbook site_with_when.yml
```
执行结果为：
```
[jshi@jjshi 01_call_simple_role]$ ansible-playbook site_with_when.yml

PLAY [all] *********************************************************************

TASK [setup] *******************************************************************
ok: [localhost]

TASK [simple : Task in role demo] **********************************************
skipping: [localhost]

PLAY RECAP *********************************************************************
localhost                  : ok=1    changed=0    unreachable=0    failed=0
```
