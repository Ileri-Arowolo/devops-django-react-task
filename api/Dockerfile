# get base image
FROM python:3.9.6-alpine

ENV Docker_HOME=/home/app/webapp  

RUN mkdir -p $Docker_HOME  

# get base image
WORKDIR $Docker_HOME  
  
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1  

# install dependencies  
RUN pip install --upgrade pip  

#Copy project to docker home directory. 
COPY . $Docker_HOME  
 
#PIP install requirements.txt  
RUN pip freeze > requirements.txt
RUN pip install django

#Django app port  
EXPOSE 8000  
#start server  
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
