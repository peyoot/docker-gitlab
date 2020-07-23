Since original sameersbn just switch to gitlab 13 and postgresql 11 in his docker-compose file. 
Here I took most stable gitlab 12 version.

gitlab: 12.10.6
postgresql 10-2
redis:5.0.9

Also, put 3 volumes in same sub-folder with docker-compose.yml file.
So you can easily move or upgrade with your backup.
Here's my 3 folers and docker-compose.yml file lists in the path:

peyoot@myhost:/home/peyoot/docker/gitlab#ls

gitlab
postgresql
redis
docker-compose.yml


If you want to move to new server. just do rsync:

rsync -avzP ./*  new-server-ip:/path

and then run "docker-compose up -d"
