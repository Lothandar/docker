#	an argument for the python version
#	by default this is for version 3.6.8, but it can be modified
#	by the docker build command:
#	docker build -t python-server \
#		--build-arg PYTHON_VERSION=2.7 .
ARG PYTHON_VERSION=3.6.8
# the base image to build from which is ready to run
# Python code immediately
FROM python:${PYTHON_VERSION}
# the working directory for docker instruction has
# been changed to where our application is going 
# to be installed
WORKDIR /opt/python-server
#copy the correct python script to the current working directory
COPY ./python-server-${PYTHON_VERSION}.py app.py

COPY index.html .

RUN sed -i "s/{{PYTHON_VERSION}}/${PYTHON_VERSION}/g" index.html

EXPOSE 9000

ENTRYPOINT ["/usr/local/bin/python", "app.py"]
