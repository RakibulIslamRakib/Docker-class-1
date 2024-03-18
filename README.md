# Docker-class-1

C:\Users\BS982.BS-982.000>**docker pull postgres**  (ignore * sign)

              Using default tag: latest
              latest: Pulling from library/postgres
              8a1e25ce7c4f: Pull complete
              002317ed8722: Pull complete
              c223965bd9a8: Pull complete
              847682431a68: Pull complete
              8d29ba654727: Pull complete
              fd133663e42b: Pull complete
              13de11c6ecda: Pull complete
              45bb35744214: Pull complete
              d4082e63ce2c: Pull complete
              269f33c511c1: Pull complete
              7cbaf3c85093: Pull complete
              f1c82efa0dcd: Pull complete
              e9d0d3c40657: Pull complete
              68bf5c580643: Pull complete
              Digest: sha256:5e027a0e4b3eebb181af3630815c087f17f867abb9bc5860b4e2a203019a04c2
              Status: Downloaded newer image for postgres:latest
              docker.io/library/postgres:latest

What's Next?
  View a summary of image vulnerabilities and recommendations → docker scout quickview postgres

C:\Users\BS982.BS-982.000>**docker run postgres**

      Error: Database is uninitialized and superuser password is not specified.
             You must specify POSTGRES_PASSWORD to a non-empty value for the
             superuser. For example, "-e POSTGRES_PASSWORD=password" on "docker run".
      
             You may also use "POSTGRES_HOST_AUTH_METHOD=trust" to allow all
             connections without a password. This is *not* recommended.
      
             See PostgreSQL documentation about "trust":
             https://www.postgresql.org/docs/current/auth-trust.html

C:\Users\BS982.BS-982.000>**docker run -e POSTGRES_PASSWORD=mysecretpassword postgres**
              The files belonging to this database system will be owned by user "postgres".
              This user must also own the server process.
              
              The database cluster will be initialized with locale "en_US.utf8".
              The default database encoding has accordingly been set to "UTF8".
              The default text search configuration will be set to "english".
              
              Data page checksums are disabled.
              
              fixing permissions on existing directory /var/lib/postgresql/data ... ok
              creating subdirectories ... ok
              selecting dynamic shared memory implementation ... posix
              selecting default max_connections ... 100
              selecting default shared_buffers ... 128MB
              selecting default time zone ... Etc/UTC
              creating configuration files ... ok
              running bootstrap script ... ok
              performing post-bootstrap initialization ... ok
              syncing data to disk ... ok
              
              
              Success. You can now start the database server using:

              pg_ctl -D /var/lib/postgresql/data -l logfile start

              initdb: warning: enabling "trust" authentication for local connections
              initdb: hint: You can change this by editing pg_hba.conf or using the option -A, or --auth-local and --auth-host, the next time you run initdb.
              waiting for server to start....2024-03-14 08:15:49.306 UTC [48] LOG:  starting PostgreSQL 16.2 (Debian 16.2-1.pgdg120+2) on x86_64-pc-linux-gnu, compiled by gcc (Debian 12.2.0-14) 12.2.0, 64-bit
              2024-03-14 08:15:49.314 UTC [48] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
              2024-03-14 08:15:49.342 UTC [51] LOG:  database system was shut down at 2024-03-14 08:15:47 UTC
              2024-03-14 08:15:49.352 UTC [48] LOG:  database system is ready to accept connections
               done
              server started
              
              /usr/local/bin/docker-entrypoint.sh: ignoring /docker-entrypoint-initdb.d/*
              
              waiting for server to shut down...2024-03-14 08:15:49.417 UTC [48] LOG:  received fast shutdown request
              .2024-03-14 08:15:49.424 UTC [48] LOG:  aborting any active transactions
              2024-03-14 08:15:49.426 UTC [48] LOG:  background worker "logical replication launcher" (PID 54) exited with exit code 1
              2024-03-14 08:15:49.426 UTC [49] LOG:  shutting down
              2024-03-14 08:15:49.433 UTC [49] LOG:  checkpoint starting: shutdown immediate
              2024-03-14 08:15:49.476 UTC [49] LOG:  checkpoint complete: wrote 3 buffers (0.0%); 0 WAL file(s) added, 0 removed, 0 recycled; write=0.014 s, sync=0.007 s, total=0.050 s; sync files=2, longest=0.004 s, average=0.004 s; distance=0 kB, estimate=0 kB; lsn=0/14EAA70, redo lsn=0/14EAA70
              2024-03-14 08:15:49.479 UTC [48] LOG:  database system is shut down
               done
              server stopped
              
              PostgreSQL init process complete; ready for start up.

              2024-03-14 08:15:49.549 UTC [1] LOG:  starting PostgreSQL 16.2 (Debian 16.2-1.pgdg120+2) on x86_64-pc-linux-gnu, compiled by gcc (Debian 12.2.0-14) 12.2.0, 64-bit
              2024-03-14 08:15:49.550 UTC [1] LOG:  listening on IPv4 address "0.0.0.0", port 5432
              2024-03-14 08:15:49.550 UTC [1] LOG:  listening on IPv6 address "::", port 5432
              2024-03-14 08:15:49.564 UTC [1] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
              2024-03-14 08:15:49.580 UTC [62] LOG:  database system was shut down at 2024-03-14 08:15:49 UTC
              2024-03-14 08:15:49.589 UTC [1] LOG:  database system is ready to accept connections
              2024-03-14 08:20:49.605 UTC [60] LOG:  checkpoint starting: time
              2024-03-14 08:20:53.854 UTC [60] LOG:  checkpoint complete: wrote 44 buffers (0.3%); 0 WAL file(s) added, 0 removed,
              0 recycled; write=4.135 s, sync=0.043 s, total=4.250 s; sync files=11, longest=0.033 s, average=0.004 s; distance=261 kB, estimate=261 kB; lsn=0/152BEC8, redo lsn=0/152BE90


   //see all running container:(open different window cmd )
   C:\Users\BS982.BS-982.000>**docker ps**
              CONTAINER ID   IMAGE                  COMMAND                  CREATED         STATUS                       PORTS      NAMES
              41f99cae71c3   postgres               "docker-entrypoint.s…"   7 minutes ago   Up 7 minutes                 5432/tcp   amazing_johnson
              34531e2ff8c4   willfarrell/autoheal   "/docker-entrypoint …"   46 hours ago    Up About an hour (healthy)              docker-autoheal-1

//docker vs virtual box
![image](https://github.com/RakibulIslamRakib/Docker-class-1/assets/56424436/fbcb6fd7-3d0d-4c3c-ac87-c1503e304abc)

deploying docker in windows( bellow 10 or older mac version not posible) , using docker toolbox we can deploy dicker container in windows v>=10 or mac new versions
![image](https://github.com/RakibulIslamRakib/Docker-class-1/assets/56424436/b7580207-2bd6-41e8-b18b-11aeea3e8743)






**docker pull redis**
**docker run redis** :-> run redis   container 
**docker run -d redis** :-> run redis   container in detach mode, it will be running in background and wi will be able to use the cmd 

**docker ps -a** : display all container

// binding port
docker run -d -p6000:6379 redis  : 6000 ->my laptop port, web browser ie localhost:6000 and 6379 bis the docker container port for redis

![image](https://github.com/RakibulIslamRakib/Docker-class-1/assets/56424436/ac492ed0-41b2-4f79-87c6-9aeda28014ea)

now we cannot bind port 6000 with any other port.
![image](https://github.com/RakibulIslamRakib/Docker-class-1/assets/56424436/6d181f6e-6fa7-45c0-8573-97faa9bec9e9)


**docker logs goofy_cartwright**:  see containers logs,  running containers have some random name that is human readable, so that we can use that instead of id ie: goofy_cartwright

lets check logs files or conf file or env in image:

C:\Users\BS982.BS-982.000>docker exec -it 571bcf4dbeda /bin/bash   (it->interective terminal, 571bcf4dbeda: container id)
root@571bcf4dbeda:/data# ls
root@571bcf4dbeda:/data# pwd
/data
root@571bcf4dbeda:/data# cd /
root@571bcf4dbeda:/# ls
bin   data  etc   lib    media  opt   root  sbin  sys  usr
boot  dev   home  lib64  mnt    proc  run   srv   tmp  var
root@571bcf4dbeda:/# env
HOSTNAME=571bcf4dbeda
REDIS_DOWNLOAD_SHA=8d104c26a154b29fd67d6568b4f375212212ad41e0c2caa3d66480e78dbd3b59
PWD=/
HOME=/root
REDIS_VERSION=7.2.4
GOSU_VERSION=1.17
TERM=xterm
REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-7.2.4.tar.gz
SHLVL=1
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
_=/usr/bin/env
OLDPWD=/data
root@571bcf4dbeda:/# exit
exit

C:\Users\BS982.BS-982.000>

**docker run vs docker start:** run command use for create a container with an image with specific version and start is used to restart an existing container

Builds JS APP & creates Docker Image:
![image](https://github.com/RakibulIslamRakib/Docker-class-1/assets/56424436/c434c753-973d-4932-a9f7-f9d132adddba)
