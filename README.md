To repoduce this bug, you have to install docker, then:

`distro=centos7 playbook=../run_test.yml tests/test.sh`

You will receive the following output:

```
/t/ansible-centos7-bug ❯❯❯ distro=centos7 playbook=../run_test.yml tests/test.sh                                                                               master ✱ ◼
Starting Docker container: geerlingguy/docker-centos7-ansible.
latest: Pulling from geerlingguy/docker-centos7-ansible
Digest: sha256:d111a71440acf4b9139fa8c1ac91f9e91806b96ba5e5416ca6b8cbd11d7444d6
Status: Image is up to date for geerlingguy/docker-centos7-ansible:latest
e1f3e8f05fa0925046c9d3e8a1dc9e41a1044df4dfde9f7738c84afe2bc9f903


Checking Ansible playbook syntax.
playbook: /etc/ansible/roles/role_under_test/tests/../run_test.yml

Running command: docker exec 1493300616 env TERM=xterm ansible-playbook /etc/ansible/roles/role_under_test/tests/../run_test.ymlUsing /etc/ansible/ansible.cfg as config file

PLAYBOOK: run_test.yml *********************************************************
1 plays in /etc/ansible/roles/role_under_test/tests/../run_test.yml

PLAY [all] *********************************************************************

TASK [setup] *******************************************************************
Using module file /usr/lib/python2.7/site-packages/ansible/modules/core/system/setup.py
<localhost> ESTABLISH LOCAL CONNECTION FOR USER: root
<localhost> EXEC /bin/sh -c '( umask 77 && mkdir -p "` echo ~/.ansible/tmp/ansible-tmp-1493300620.24-69813047861230 `" && echo ansible-tmp-1493300620.24-69813047861230="` echo ~/.ansible/tmp/ansible-tmp-1493300620.24-69813047861230 `" ) && sleep 0'
<localhost> PUT /tmp/tmpGA2HqE TO /root/.ansible/tmp/ansible-tmp-1493300620.24-69813047861230/setup.py
<localhost> EXEC /bin/sh -c 'chmod u+x /root/.ansible/tmp/ansible-tmp-1493300620.24-69813047861230/ /root/.ansible/tmp/ansible-tmp-1493300620.24-69813047861230/setup.py && sleep 0'
<localhost> EXEC /bin/sh -c '/usr/bin/python /root/.ansible/tmp/ansible-tmp-1493300620.24-69813047861230/setup.py; rm -rf "/root/.ansible/tmp/ansible-tmp-1493300620.24-69813047861230/" > /dev/null 2>&1 && sleep 0'
ok: [localhost]

TASK [test : Update yum packages] **********************************************
task path: /etc/ansible/roles/role_under_test/roles/test/tasks/main.yml:2
Using module file /usr/lib/python2.7/site-packages/ansible/modules/core/packaging/os/yum.py
<localhost> ESTABLISH LOCAL CONNECTION FOR USER: root
<localhost> EXEC /bin/sh -c '( umask 77 && mkdir -p "` echo ~/.ansible/tmp/ansible-tmp-1493300622.22-231217596451130 `" && echo ansible-tmp-1493300622.22-231217596451130="` echo ~/.ansible/tmp/ansible-tmp-1493300622.22-231217596451130 `" ) && sleep 0'
<localhost> PUT /tmp/tmp43vvs3 TO /root/.ansible/tmp/ansible-tmp-1493300622.22-231217596451130/yum.py
<localhost> EXEC /bin/sh -c 'chmod u+x /root/.ansible/tmp/ansible-tmp-1493300622.22-231217596451130/ /root/.ansible/tmp/ansible-tmp-1493300622.22-231217596451130/yum.py && sleep 0'
<localhost> EXEC /bin/sh -c '/usr/bin/python /root/.ansible/tmp/ansible-tmp-1493300622.22-231217596451130/yum.py; rm -rf "/root/.ansible/tmp/ansible-tmp-1493300622.22-231217596451130/" > /dev/null 2>&1 && sleep 0'
changed: [localhost] => {
    "changed": true,
    "invocation": {
        "module_args": {
            "conf_file": null,
            "disable_gpg_check": false,
            "disablerepo": null,
            "enablerepo": null,
            "exclude": null,
            "install_repoquery": true,
            "list": null,
            "name": [
                "*"
            ],
            "state": "latest",
            "update_cache": false,
            "validate_certs": true
        },
        "module_name": "yum"
    },
    "msg": "/usr/share/man/man5/cert8.db.5.gz: No such file or directory\ncannot reconstruct rpm from disk files\n/usr/share/man/man1/certutil.1.gz: No such file or directory\ncannot reconstruct rpm from disk files\n",
    "rc": 0,
    "results": [
        "Loaded plugins: fastestmirror, ovl\nLoading mirror speeds from cached hostfile\n * base: mirror.de.leaseweb.net\n * epel: mirror.de.leaseweb.net\n * extras: ftp.rrzn.uni-hannover.de\n * updates: mirror.de.leaseweb.net\nResolving Dependencies\n--> Running transaction check\n---> Package ansible.noarch 0:2.2.1.0-1.el7 will be updated\n---> Package ansible.noarch 0:2.3.0.0-3.el7 will be an update\n---> Package bind-license.noarch 32:9.9.4-38.el7_3.2 will be updated\n---> Package bind-license.noarch 32:9.9.4-38.el7_3.3 will be an update\n---> Package device-mapper.x86_64 7:1.02.135-1.el7_3.3 will be updated\n---> Package device-mapper.x86_64 7:1.02.135-1.el7_3.4 will be an update\n---> Package device-mapper-libs.x86_64 7:1.02.135-1.el7_3.3 will be updated\n---> Package device-mapper-libs.x86_64 7:1.02.135-1.el7_3.4 will be an update\n---> Package nss.x86_64 0:3.28.2-1.6.el7_3 will be updated\n---> Package nss.x86_64 0:3.28.4-1.0.el7_3 will be an update\n---> Package nss-sysinit.x86_64 0:3.28.2-1.6.el7_3 will be updated\n---> Package nss-sysinit.x86_64 0:3.28.4-1.0.el7_3 will be an update\n---> Package nss-tools.x86_64 0:3.28.2-1.6.el7_3 will be updated\n---> Package nss-tools.x86_64 0:3.28.4-1.0.el7_3 will be an update\n---> Package nss-util.x86_64 0:3.28.2-1.1.el7_3 will be updated\n---> Package nss-util.x86_64 0:3.28.4-1.0.el7_3 will be an update\n--> Finished Dependency Resolution\n\nDependencies Resolved\n\n================================================================================\n Package                Arch       Version                    Repository   Size\n================================================================================\nUpdating:\n ansible                noarch     2.3.0.0-3.el7              epel        5.7 M\n bind-license           noarch     32:9.9.4-38.el7_3.3        updates      83 k\n device-mapper          x86_64     7:1.02.135-1.el7_3.4       updates     269 k\n device-mapper-libs     x86_64     7:1.02.135-1.el7_3.4       updates     333 k\n nss                    x86_64     3.28.4-1.0.el7_3           updates     873 k\n nss-sysinit            x86_64     3.28.4-1.0.el7_3           updates      58 k\n nss-tools              x86_64     3.28.4-1.0.el7_3           updates     496 k\n nss-util               x86_64     3.28.4-1.0.el7_3           updates      73 k\n\nTransaction Summary\n================================================================================\nUpgrade  8 Packages\n\nTotal download size: 7.8 M\nDownloading packages:\nNo Presto metadata available for epel\nDelta RPMs reduced 1.7 M of updates to 609 k (65% saved)\nFinishing delta rebuilds of 3 package(s) (1.4 M)\nSome delta RPMs failed to download or rebuild. Retrying..\n--------------------------------------------------------------------------------\nTotal                                              5.7 MB/s | 8.0 MB  00:01     \nRunning transaction check\nRunning transaction test\nTransaction test succeeded\nRunning transaction\n  Updating   : nss-util-3.28.4-1.0.el7_3.x86_64                            1/16 \n  Updating   : nss-3.28.4-1.0.el7_3.x86_64                                 2/16 \n  Updating   : nss-sysinit-3.28.4-1.0.el7_3.x86_64                         3/16 \n  Updating   : 7:device-mapper-1.02.135-1.el7_3.4.x86_64                   4/16 \n  Updating   : 7:device-mapper-libs-1.02.135-1.el7_3.4.x86_64              5/16 \n  Updating   : nss-tools-3.28.4-1.0.el7_3.x86_64                           6/16 \n  Updating   : 32:bind-license-9.9.4-38.el7_3.3.noarch                     7/16 \n  Updating   : ansible-2.3.0.0-3.el7.noarch                                8/16 \n  Cleanup    : 32:bind-license-9.9.4-38.el7_3.2.noarch                     9/16 \n  Cleanup    : ansible-2.2.1.0-1.el7.noarch                               10/16 \n  Cleanup    : nss-tools-3.28.2-1.6.el7_3.x86_64                          11/16 \n  Cleanup    : nss-sysinit-3.28.2-1.6.el7_3.x86_64                        12/16 \n  Cleanup    : nss-3.28.2-1.6.el7_3.x86_64                                13/16 \n  Cleanup    : 7:device-mapper-1.02.135-1.el7_3.3.x86_64                  14/16 \n  Cleanup    : 7:device-mapper-libs-1.02.135-1.el7_3.3.x86_64             15/16 \n  Cleanup    : nss-util-3.28.2-1.1.el7_3.x86_64                           16/16 \n  Verifying  : nss-util-3.28.4-1.0.el7_3.x86_64                            1/16 \n  Verifying  : ansible-2.3.0.0-3.el7.noarch                                2/16 \n  Verifying  : nss-3.28.4-1.0.el7_3.x86_64                                 3/16 \n  Verifying  : nss-sysinit-3.28.4-1.0.el7_3.x86_64                         4/16 \n  Verifying  : 7:device-mapper-libs-1.02.135-1.el7_3.4.x86_64              5/16 \n  Verifying  : 32:bind-license-9.9.4-38.el7_3.3.noarch                     6/16 \n  Verifying  : 7:device-mapper-1.02.135-1.el7_3.4.x86_64                   7/16 \n  Verifying  : nss-tools-3.28.4-1.0.el7_3.x86_64                           8/16 \n  Verifying  : 32:bind-license-9.9.4-38.el7_3.2.noarch                     9/16 \n  Verifying  : 7:device-mapper-1.02.135-1.el7_3.3.x86_64                  10/16 \n  Verifying  : nss-tools-3.28.2-1.6.el7_3.x86_64                          11/16 \n  Verifying  : ansible-2.2.1.0-1.el7.noarch                               12/16 \n  Verifying  : nss-3.28.2-1.6.el7_3.x86_64                                13/16 \n  Verifying  : nss-sysinit-3.28.2-1.6.el7_3.x86_64                        14/16 \n  Verifying  : nss-util-3.28.2-1.1.el7_3.x86_64                           15/16 \n  Verifying  : 7:device-mapper-libs-1.02.135-1.el7_3.3.x86_64             16/16 \n\nUpdated:\n  ansible.noarch 0:2.3.0.0-3.el7                                                \n  bind-license.noarch 32:9.9.4-38.el7_3.3                                       \n  device-mapper.x86_64 7:1.02.135-1.el7_3.4                                     \n  device-mapper-libs.x86_64 7:1.02.135-1.el7_3.4                                \n  nss.x86_64 0:3.28.4-1.0.el7_3                                                 \n  nss-sysinit.x86_64 0:3.28.4-1.0.el7_3                                         \n  nss-tools.x86_64 0:3.28.4-1.0.el7_3                                           \n  nss-util.x86_64 0:3.28.4-1.0.el7_3                                            \n\nComplete!\n"
    ]
}

TASK [test : install sssd client] **********************************************
task path: /etc/ansible/roles/role_under_test/roles/test/tasks/main.yml:5
An exception occurred during task execution. The full traceback is:
Traceback (most recent call last):
  File "/usr/lib/python2.7/site-packages/ansible/executor/task_executor.py", line 126, in run
    display.debug("_execute() done")
  File "/usr/lib/python2.7/site-packages/ansible/executor/task_executor.py", line 502, in _execute
    retries = 1
  File "/usr/lib/python2.7/site-packages/ansible/plugins/action/normal.py", line 45, in run
    results = merge_hash(results, self._execute_module(tmp=tmp, task_vars=task_vars, wrap_async=wrap_async))
TypeError: _execute_module() got an unexpected keyword argument 'wrap_async'

fatal: [localhost]: FAILED! => {
    "failed": true,
    "msg": "Unexpected failure during module execution.",
    "stdout": ""
}
	to retry, use: --limit @/etc/ansible/roles/role_under_test/run_test.retry

PLAY RECAP *********************************************************************
localhost                  : ok=2    changed=1    unreachable=0    failed=1
```
