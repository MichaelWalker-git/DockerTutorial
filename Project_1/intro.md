## History of Docker

#### Movement from Mainframe to PC
#### Baremetal to Virtual
Movement from datacenter to virtual, VM. 

#### Datacenters to Cloud
Cloud, easy, cheap, level of scale, disposable

#### Containers
- Serverless, functions as a service, run inside of containers
- Focused on the migration experience.
- Good for developers

#### Docker Pros
- Speed of deployment, develor, build, test, deploy, update, recover

#### Matrix fo hell breeds complexity
- Static website
- WEb frontend
- Background workers
- User DB
- Analytics DB
- Queue

#### Allows you package, test, deploy consistently!
- Maintenance / complexity drains budgets so innovation suffers,
- Stalled initiatives, frees up the tasks 

Example company
- Paypal 
> 18 Month project, migrated 700 + apps, now 150k containers, 50%+ dev productivity boost

- Metlife
> 70% reduction in VM costs, 67% fewer CPUs, 66% cost reduction, 10x avg CPU util

#### Introduction to getting started
Docker daemon (mac); docker version -> Means that server is up and running

> Image vs Container
- Image is an aplicaton we want to run
- Container is an instance of that image running as a process
- You can have many containers running off the same image
- Our image will be the Nginx web server

> docker container run --publish 80:80 --detach nginx
- Runs docker in the background; 
- Gives us a unique docker id
- No name specified

> docker container stop <first few numbers of container id>
- Stops that container

> docker container ls
- Lists the running containers

> docker container run --publish 80:80 --detach --name webhost nginx
- Named the container (has to be unique)

>docker container logs webhost
- Gets log files for container

> docker container top webhost 
- See processes inside of container

> docker container rm <containerId> <containerId>
- Cannot stop, but can remove stopped containers

> docker container rm -f <containerId>
- Force stop and remove

> docker container run --publish 8080:80 --name webhost -d nginx:1.11 nginx -T
- Change host listening port "8080"
- Change version of image "1.11"
- Change CMD run on start "-T"


##### Difference between Container vs Virtual Machines
- Containers are not mini VMs
- They are just processes on your local machine

> docker run --name mongo -d mongo
- Runs mongo 

> ps aux
- Show me all running processes

#### Manage multiple containers
>  docker container run -d -p 3306:3306 --name mysql -e MYSQL_RANDOM_ROOT_PASSWORD=yes mysql
GENERATED ROOT PASSWORD: atahkeet1Eitohw1ne8coegoo1aed2ee
