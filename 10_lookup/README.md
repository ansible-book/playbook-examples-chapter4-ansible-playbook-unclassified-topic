
在本目录下，执行下面的命令来查看测试结果:

```
ansible-playbook site*.yml
```
----------

请参考输出的结果:
```
ansible-playbook site_lookup_file.yml
```
结果为：
```
[jshi@jjshi 10_lookup]$ ansible-playbook site_lookup_file.yml

PLAY [all] *********************************************************************

TASK [setup] *******************************************************************
ok: [jshi-test-02.rhev]

TASK [debug] *******************************************************************
ok: [jshi-test-02.rhev] => {
    "msg": "the value of /etc/hosts is 127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4\n::1         localhost localhost.localdomain localhost6 localhost6.localdomain6\n\n192.168.50.211 jjshi.home\n\n192.168.50.138 fedora.local\n\n192.168.122.135 win7.local\n\n#VM on rhev\n10.66.208.242 ansibletower.rhev\n10.66.208.194 jshi-test-01.rhev\n10.66.208.212 jshi-test-02.rhev"
}

PLAY RECAP *********************************************************************
jshi-test-02.rhev          : ok=2    changed=0    unreachable=0    failed=0   
```


```
[jshi@jjshi 10_lookup]$ ansible-playbook site_lookup_csv.yml

PLAY [all] *********************************************************************

TASK [setup] *******************************************************************
ok: [jshi-test-02.rhev]

TASK [debug] *******************************************************************
ok: [jshi-test-02.rhev] => {
    "msg": "The atomic number of Lithium is 3"
}

TASK [debug] *******************************************************************
ok: [jshi-test-02.rhev] => {
    "msg": "The atomic mass of Lithium is 6.94"
}

PLAY RECAP *********************************************************************
jshi-test-02.rhev          : ok=3    changed=0    unreachable=0    failed=0  
```
