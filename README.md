# docker-kubernets
By Udacity >>> https://www.udacity.com/course/scalable-microservices-with-kubernetes--ud615

## Resources

* https://github.com/udacity/ud615
* https://github.com/askcarter/io16

## Notes

* Set GCLOUD zone
```
$ gcloud config set compute/zone europe-west1-b
```

* Check configuration
```
$ gcloud config list
```

The compute machine/environment is up and running on the right zone.

* Create an instance for a VM
``` 
$ gcloud compute instances create ubuntu \
--image-project ubuntu-os-cloud \
--image ubuntu-1604-xenial-v20160420c
```

* SSH into the newly created instance and set it up
```
$ gcloud compute ssh ubuntu
$ sudo apt-get update
$ sudo apt-get install nginx
$ nginx -v
```

* Check or run the web server
```
$ sudo systemctl start nginx
$ cat /etc/init/nginx.conf
```

* Install docker
```
$ sudo apt-get install docker.io
$ sudo docker images
```

* Pull Docker images
```
$ sudo docker pull nginx:1.10.0
$ sudo docker images
$ sudo dpkg -l | grep nginx
```
If version of nginx from native package and Docker are different, you need to update the VM instance:
```
sudo apt-get update
sudo apt-get install nginx
```

* Overview of docker commands and containers
```
$ docker --help
$ sudo docker ps
```

* Run the first instance
```
$ sudo docker run -d nginx:1.10.0
```

* Check if it's up
```
sudo docker ps
```

* Run a different version of nginx
```
$ sudo docker run -d nginx:1.9.3
```

* Run another version of nginx
```
$ sudo docker run -d nginx:1.10.0
```

* Check how many instances are running
```
sudo docker ps
sudo ps aux | grep nginx
```

* Inspect containers
```
$ sudo docker inspect <id_hex>
$ sudo docker inspect <random_name>
```

* Connect to the nginx using the internal IP

Get the internal IP address either copying from the full inspect file or by assigning it to a shell variable:
```
$ CN="sharp_bartik"
$ CIP=$(sudo docker inspect --format '{{ .NetworkSettings.IPAddress }}' $CN)
$ curl  http://$CIP
```
You can also get all instance IDs and their corresponding IP addresses by doing this:

```
$ sudo docker inspect -f '{{.Name}} - {{.NetworkSettings.IPAddress }}' $(sudo docker ps -aq)
```


