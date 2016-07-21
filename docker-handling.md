# Containers handling

**List** running containers:
- `docker ps`
- all `docker ps -a`

Allocates a pseudo-TTY or **terminal** and assign it to the container:
- `docker attach <container>`

Spot changes in containers' filesystem:
- `docker diff <uid>`
    - C: file changed
    - A: file added
    - D: file delete

**Stop** a container:
- `docker stop <uid> `
    - launch SIGTERM -15
    - if fail launch SIGKILL -9

**Start** a container (but not attach):
- `docker start <uid>`
- `docker restart <uid>`

**Freeze** with pause and unpause

Print **container metadata**:
- `docker inspect <uid>`
- sample output: ```[
   {
       "Id": "3ce51710b34f5d6da95e0a340d32aa2e6cf64857fb8cdb2a6c38f7c56f448143",
       "Created": "2015-10-25T22:44:17.854367116Z",
       "Path": "python",
       "Args": [
           "app.py"
       ],
       "State": {
           "Status": "running",
           "Running": true,
           "Paused": false,
           "Restarting": false,
           "OOMKilled": false,
  ...```

**Delete** a container:
- `docker rm <uid>`

Delete an **image**:
- `docker rmi <iud>`








