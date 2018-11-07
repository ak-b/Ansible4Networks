# NSO_Ansible_Playbooks
Ansible roles to invoke NSO over JSONRPC

#Ansible Tower
Connecting to docker container for task to figure out inventory path

#AKBANSAL-M-R0GA:awx akbansal$ docker ps
CONTAINER ID        IMAGE                     COMMAND                  CREATED             STATUS              PORTS                                NAMES
7434cc2b4cc3        ansible/awx_task:latest   "/tini -- /bin/sh -c…"   8 weeks ago         Up 2 hours          8052/tcp                             awx_awx_task_1
39511f113321        ansible/awx_web:latest    "/tini -- /bin/sh -c…"   8 weeks ago         Up 2 hours          0.0.0.0:80->8052/tcp                 awx_awx_web_1
a67421b18413        rabbitmq:3                "docker-entrypoint.s…"   8 weeks ago         Up 2 hours          4369/tcp, 5671-5672/tcp, 25672/tcp   awx_rabbitmq_1
af8682d040b9        memcached:alpine          "docker-entrypoint.s…"   8 weeks ago         Up 2 hours          11211/tcp                            awx_memcached_1
b09b771142ce        postgres:9.6              "docker-entrypoint.s…"   8 weeks ago         Up 2 hours          5432/tcp                             awx_postgres_1
#AKBANSAL-M-R0GA:awx akbansal$ docker exec -it awx_awx_task_1 bash
[root@awx awx]# ls
beat.db  favicon.ico  projects  public  supervisord.log  supervisord.pid  venv  wsgi.py
[root@awx awx]# cd projects/
[root@awx projects]# ls
_6__my_test  _6__my_test.lock
[root@awx projects]# cd _6__my_test
[root@awx _6__my_test]# ls
ansible.cfg  group_vars  host_vars  inventory  NSO_Ansible_Log  preconf_ASA.yml  query_asa.yml  README.md  roles
[root@awx _6__my_test]# cd inventory/
[root@awx inventory]# ls
all.yaml  nso-qa-lab.yml
[root@awx inventory]# pwd
/var/lib/awx/projects/_6__my_test/inventory
