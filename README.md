### Install docker

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"


sudo apt-get update

apt-cache policy docker-ce

sudo apt-get install -y docker-ce

sudo systemctl status docker

sudo usermod -aG docker ${USER}

su - ${USER}

id -nG

docker

docker --version

```

### Install docker-compose

[Latest docker-compose](https://github.com/docker/compose/releases)

```
sudo curl -L https://github.com/docker/compose/releases/download/1.29.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

$ sudo chmod +x /usr/local/bin/docker-compose

docker-compose --version


```

## Install Other Databases

To Run Redis with redisinsight

```
docker run -d --name redis-stack -p 6379:6379 -p 9001:8001 redis/redis-stack:latest

navigate to <ipaddress>:9001 to access redisinsight

to stop container run
docker stop redis-stack


```

## To Run Dgraph

```
docker run --name dgraph -d -p "8080:8080" -p "9080:9080" -v db:/dgraph dgraph/standalone:latest

docker run --name ratel -d -p "9000:8000" dgraph/ratel:latest


```

### navigate to ipaddress:9000 navigate to ipaddress port 8080

## Docker Command to free up space if required

```
Stop all containers
sudo docker container stop $(docker container ls -aq)
sudo docker system prune -a -f

```
