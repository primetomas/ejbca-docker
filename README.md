# Docker build EJBCA Server From Scratch

## Usage

Create initial volume: ./setup.sh

Create an .env file:

    httpsserver_hostname=ejbca.example.com
    database_host=psql
    database_name=ejbcadev
    database_username=ejbcadev
    database_password=very***bad***database***password
    
    # Either postgres or mysql
    database_type=postgres
    database_port=5432
    #database_type=mysql
    
    superadmin_cn=SuperAdmin2020
    ca_name=Management
    BASE_DN=O=My Example CA 2020,C=DE

Build container

    docker-compose build

# Install EJBCA Container

    docker-compose up

First start builds EJBCA and terminates then

# Let's Go

Next start fires up EJBCA instance

    docker-compose up && docker-compose logs --tail=20 -ft

or use simply enclosed script

    restart

# Security Considerations

This builds an EJBCA as is. It is strongly recommended to use a reverse Proxy
server in front of EJBCA to filter access.
Wildfly opens some ports which should not be exposed to Internet.

# Content

Container is built an Centos8, Wildfly 14.0.1 and EJBCA 6.15.2.5 Community (r33900)

