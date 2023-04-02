FROM python:3.10-slim-buster

# Inside Container
# Make a new folder inside container
WORKDIR /backend-flask/python

# Outside Container -> Inside Container
# This contains the llibraries to install for the app to run
COPY requirements.txt requirements.txt

# Inside Container
# Install the python images used for the app to run
RUN pip3 install -r requirements.txt

#Outside Container -> Inside Container
# . means everything in the current directory
# first period . - /backend-flask (outside container)
# second period . /backend-flask (inside container)
COPY . . 

# Set Environment Variables (Env Vars)
# Inside Container and will remain set when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

# CMD (Command)
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]