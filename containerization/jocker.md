# Jocker
[Jocker](https://github.com/jolie/jocker) is a Jolie service which provides a Jolie interface of the [HTTP docker APIs](https://docs.docker.com/engine/api/v1.29/). Thanks to Jocker it is possible to interact with a docker server just as it is a Jolie service. At [this link](https://github.com/jolie/jocker/blob/master/InterfaceAPI.iol) it is possible to check the API supported by Jocker.

Jocker is available as a docker container, just type the following commands for activating a Jocker instance:
```
docker pull jolielang/jocker
docker run -it -p 8008:8008 --name jocker -v /var/run:/var/run jolielang/jocker
```
**Important notes**
* Jocker is listening on the container internal port `8008`, thus if you need to change it, just configure properly the container when running it using the parameter `-p 8008:8008`.
* Jocker communicates with the docker server using the localsocket `/var/run/docker.sock` as it is suggested by docker documentation. Thus, pay attention when creating the jocker container to share the host volume where such a socket is available by setting parameter `-v /var/run:/var/run`.
* At the present Jocker is an experimental project, so use with cautions.

![](../.gitbook/assets/jocker.png)

Once installed, it is possible to call Jocker as a usual Jolie service.

## Example: creating a Jolie orchestrator for deploying a Jolie system into docker
In this example we show how to build a Jolie orchestrator which is able to deploy a Jolie system by exploiting the Jocker APIs.
The full code of the example can be checked [here](https://github.com/jolie/examples/tree/master/06_containers/05_jocker).