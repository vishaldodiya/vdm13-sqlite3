# Sqlite3 Docker Container

## Dockerfile

### Alpine as Base image (which is lightweight)

`FROM alpine:latest`

### Downloading latest sqlite source code

`RUN wget http://www.sqlite.org/2017/sqlite-autoconf-3170000.tar.gz`

### Unzip tar file 

`RUN tar xvfz sqlite-autoconf-3170000.tar.gz`

### Install alpine sdk as a prerequisite for sqlite installation

`RUN apk add --update alpine-sdk`

### Some configuration and installation

`RUN ./sqlite-autoconf-3170000/configure --prefix=/usr`

`RUN make`

`RUN make install`

`RUN rm sqlite-autoconf-3170000.tar.gz`