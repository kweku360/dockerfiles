##Base Image for impart Engine code name Carina
**Features**

1. basic setup

2. supervisor-ssh-apache2

3. Runs On ubuntu base image

**Installation**
DOCKER BUILD

$ `docker build --rm -t kweku360/carina-base .`

This build is done inside the project folder

 or

$ `docker build --rm -t kweku360/carina-base <location of dockerfile folder>`

**notes**
supervisord.conf must exist in sourcefile folder in project folder.

Password :`theProfit` change password after ssh login or us SHA -Keys
