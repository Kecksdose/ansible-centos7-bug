To repoduce this bug, you have to install docker, then:

`distro=centos7 playbook=../run_test.yml tests/test.sh`

You will receive the following output:

```
distro=centos7 playbook=../run_test.yml tests/test.sh
Starting Docker container: geerlingguy/docker-centos7-ansible.
latest: Pulling from geerlingguy/docker-centos7-ansible
Digest: sha256:d111a71440acf4b9139fa8c1ac91f9e91806b96ba5e5416ca6b8cbd11d7444d6


To repoduce this bug, you have to install docker, then:
Status: Image is up to date for geerlingguy/docker-centos7-ansible:latest
945fc8c6c5c2123bd568eb50ff36027d7b385484b4097a2ac374948203e9c874


Checking Ansible playbook syntax.
playbook: /etc/ansible/roles/role_under_test/tests/../run_test.yml

Running command: docker exec 1493300256 env TERM=xterm ansible-playbook /etc/ansible/roles/role_under_test/tests/../run_test.yml
PLAY [all] *********************************************************************

TASK [setup] *******************************************************************
ok: [localhost]

TASK [test : Update yum packages] **********************************************
changed: [localhost]

TASK [test : install sssd client] **********************************************
An exception occurred during task execution. To see the full traceback, use -vvv. The error was: TypeError: _execute_module() got an unexpected keyword argument 'wrap_async'
fatal: [localhost]: FAILED! => {"failed": true, "msg": "Unexpected failure during module execution.", "stdout": ""}
	to retry, use: --limit @/etc/ansible/roles/role_under_test/run_test.retry

PLAY RECAP *********************************************************************
localhost                  : ok=2    changed=1    unreachable=0    failed=1
```
