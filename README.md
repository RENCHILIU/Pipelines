# Note

This is a Github Action template which builds Springboot project and push to Dockerhub(https://hub.docker.com/repository/docker/renchi/java_pipeline/general). 

# Template file 
https://github.com/RENCHILIU/SpringbootPipeline/blob/main/.github/workflows/docker_image.yml

# Test 
```
docker pull renchi/java_pipeline
docker run -p 8080:8080 renchi/java_pipeline:latest

curl localhost:8080/api/hello
```

