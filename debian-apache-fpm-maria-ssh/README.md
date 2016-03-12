# Warning
1) You can access to the web server by ssh only if you fill the SSH_KEY param in the yaml file  
2) The db container will lost its data when stopped. To persist data make a directory somwehere on your local system and add a volume in the docker-compose.yml, for example:  
```yml
db:
    image: mysql
    ports:
        - 33060:3306
    environment:
        MYSQL_DATABASE: website
        MYSQL_ALLOW_EMPTY_PASSWORD: "yes"
	volumes:
        - /somwhere/on/my/local/machine/:/var/lib/mysql
```