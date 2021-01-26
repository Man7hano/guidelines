# Docker :whale:

## Dockerfiles

- Dockerfiles are build in read-only layers
- Ephemeral, stopped, destroyed and reproducible with minimum effort
- Current working directory of docker build is called `build context`
- To build the image run `docker build .` (don't forget the .)

```dockerfile
FROM ubuntu:18.04
COPY . /app
RUN make /app
CMD python /app/app.py
```

- Most common layers:
   - `FROM` creates a layer from the ubuntu:18.04 Docker image.
   - `COPY` adds files from your Docker client’s current directory
   - `RUN` builds your application with make
   - `CMD` specifies what command to run within the container
