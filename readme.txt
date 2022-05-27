     WSL 세팅시



DOCKER DNS 세팅

/etc/docker/daemon.json
{
   "dns": ["8.8.8.8"]
}


WSL DNS에러 수정

Create a file: /etc/wsl.conf.
Put the following lines in the file
[network]
generateResolvConf = false
In a cmd window, run wsl --shutdown
Restart WSL2
Create a file: /etc/resolv.conf. If it exists, replace existing one with this new file.
Put the following lines in the file
nameserver 8.8.8.8
Repeat step 3 and 4. You will see git working fine now.


docker-compose -f mysql-redis-docker-compose.yml up -d
