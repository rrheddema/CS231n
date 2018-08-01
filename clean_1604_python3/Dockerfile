FROM ubuntu:16.04

# Update
RUN apt-get update && apt-get install -y python3 python3-pip python3-virtualenv python3-venv build-essential libssl-dev libffi-dev python-dev && apt-get clean
RUN pip3 install --upgrade pip
RUN pip install jupyter
