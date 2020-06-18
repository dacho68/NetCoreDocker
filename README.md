# NetCoreDocker

This sample is taken from https://docs.microsoft.com/en-us/dotnet/core/docker/build-container?tabs=windows


Build image
```
docker build -t counter-image -f Dockerfile .
```

Create image
```
docker create --name core-counter counter-image
```
Run and attach
```
docker start core-counter

docker attach --sig-proxy=false core-counter
```

Delete Container
```
docker stop core-counter
```

Run with -it option.  This the -it option you dont have to stop. When control-c is press the container will exit and stop. 
```
docker run -it --rm counter-image
```
It will run 3 times then stop everything
```
docker run -it --rm counter-image 3
```
Remove counter-image

```
docker rmi counter-image:latest
docker rmi mcr.microsoft.com/dotnet/core/aspnet:3.1
```