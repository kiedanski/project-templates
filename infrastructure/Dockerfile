FROM python:3.10.4-buster
ENV PYTHONBUFFERED 1
ENV PYTHONPATH "${PYTHONPATH}:/home/${USER}/workspace"
ARG USER=worker

RUN pip install --upgrade pip

RUN useradd -ms /bin/bash ${USER} 
USER ${USER}

COPY infrastructure/requirements/base.txt /tmp/base.txt
RUN pip install --user -r /tmp/base.txt

COPY infrastructure/requirements/devel.txt /tmp/devel.txt
RUN pip install --user -r /tmp/devel.txt

WORKDIR /home/${USER}/workspace