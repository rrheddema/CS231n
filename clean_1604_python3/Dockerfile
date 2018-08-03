FROM ubuntu:16.04

# Update
RUN apt-get update              \
    && apt-get install -y       \
        python3                 \
        python3-pip             \
        python3-virtualenv      \
        python3-venv            \
        build-essential         \
        libssl-dev              \
        libffi-dev              \
        python-dev              \
        python-virtualenv       \
        libtiff5-dev            \
        libjpeg8-dev            \
        zlib1g-dev              \
        libfreetype6-dev        \
        liblcms2-dev            \
        libwebp-dev             \
        tcl8.6-dev              \
        tk8.6-dev               \
        python-tk               \
        libncurses5-dev         \
        python3-tk              \
    && apt-get clean
RUN pip3 install --upgrade pip
RUN pip install jupyter
