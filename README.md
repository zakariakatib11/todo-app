sevice :
 app:
  build:
  ports:
    -.:/app
  environment:
   - MYSQL_HOST=db
   - MYSQL_USER=root
   - MYSQL_PASSWORD=iir4
   - MYSQL_DB=todos
   - command : sh -c "yarn install && yarn dev"
   - depends_on:
       -db
     db:
       image: mysql:5.7
       environment:
           - MYSQL_ROOT_PASWWORD=iir4
           - MYSQL_DATABASE=todos
        volumes:
           - todo-mysql-data:/var/lib/mysql
     volumes:
        todo-mysqm-data  
