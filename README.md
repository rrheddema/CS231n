# CS231n
Files related to CS231n assignments

## Setup

There are different ways to work on the assignment. http://cs231n.github.io/assignments2017/assignment1/
We attempt to work locally, and we will define a setup with Docker so that we can proceed with the 16.04 with Python 3 approach on an e.g. 14.04 machine. The assignment requires jupyter.

### Working locally with Docker

**Build it**
```bash
> docker build . -t clean_1604_python3
```

**List**
```bash
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
clean_1604_python3                      latest              af2c207c5c79        3 minutes ago       548MB
```

**Run with volume mapping**
```bash
> docker run -dit -v ${PWD}:/tmp -p 8888:8888 clean_1604_python3
```
Make e.g. the data and assignment information available in the pwd.
```
.
  |-clean_1604_python3
  |-assignment1
  |  |-cs231n
  |  |  |-datasets
  |  |  |-classifiers
```
Map port 8888 so that you can use jupyter

**List containers**
```bash
> docker ps
CONTAINER ID        IMAGE                COMMAND             CREATED             STATUS              PORTS                    NAMES
dbd09e42e739        clean_1604_python3   "/bin/bash"         4 seconds ago       Up 3 seconds        0.0.0.0:8888->8888/tcp   condescending_brahmagupta
```

**Work on it**
```bash
> docker exec -it dbd09e42e739 bash
root@dbd09e42e739:/#
```

**Jupyter**

Activate the virtual environment (after setting it up accordingly to the assignment)
Small remark (2018083): in requirements.txt site==0.0.1 is mentioned, it seems not to work anymore, so remove it before running pip install.
```
cd /tmp/assignment1
source .env/bin/activate
```
And start jupyter
```bash
jupyter notebook --ip=0.0.0.0 --port=8888 
```
unless it complains about root users running jupyter, then use:
```bash
jupyter notebook --ip=0.0.0.0 --port=8888  --allow-root
```

**Stop**
```bash
> docker stop dbd09e42e739
```
