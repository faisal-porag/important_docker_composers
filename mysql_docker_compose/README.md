#### Understanding the Docker Compose YAML File

This file defines two services, `mysql` and `adminer`, which are responsible for running the MySQL database and Adminer, a web-based database management tool.

`version: "3.9"`: This line specifies the version of the Docker Compose file format being used.

`mysql service`:

- `image: mariadb:10.8.3`: This line specifies the Docker image to use for the MySQL database. In this case, we're using the official MariaDB image, version 10.8.3.
  
- `command: --default-authentication-plugin=mysql_native_password`: This line sets the default authentication plugin for MySQL to`mysql_native_password`. This let's you connect to MySQL using password.
  
- `restart: always`: This line ensures that the MySQL container will always restart if it stops or crashes.
  
- `environment: MYSQL_ROOT_PASSWORD: root`: This line sets an environment variable to configure the root password for the MySQL database.
  
- `ports: - 3306:3306`: This line maps the default MySQL port (3306) from the container to the host machine.

  
`adminer service`:

- `image: adminer`: This line specifies the Docker image to use for Adminer, a web-based database management tool.
  
- `restart: always`: This line ensures that the Adminer container will always restart if it stops or crashes.
  
- `ports: - 8085:8085`: This line maps port 8080 from the container to the host machine, allowing access to the Adminer web interface.
  

#### How to Use Docker Compose to Run the MySQL Database
To run the MySQL database using the provided Docker Compose file, follow these steps:

- Install Docker and Docker Compose on your system if you haven't already.
- Save the example Docker Compose YAML file in a directory on your machine as `docker-compose.yml`.
- Open a terminal or command prompt, and navigate to the directory containing the `docker-compose.yml` file.
- Run the following command to start the MySQL and Adminer containers `docker-compose up -d`

This command will pull the necessary images (if not already present) and create the containers as defined in the `docker-compose.yml` file. 
The `-d` flag runs the containers in detached mode, allowing you to continue using the terminal. Skip the `-d` flag and then you can easily stop the containers later by pressing `Ctrl+C`.

Once the containers are running, you can access the Adminer web interface by opening a web browser and navigating to `http://localhost:8085`.


#### Connecting to the MySQL Database
##### From Adminer:

In the Adminer web interface, enter the following details to connect to the MySQL database:

- System: MariaDB or MySQL (depending on the Adminer version)
- Server: mysql
- Username: root
- Password: root
Then, click "Login" to connect to the database.

##### From a system-installed tool / from outside Docker (eg. app running locally)

If you're using a database management tool installed on your system (e.g., MySQL Workbench or TablePlus), use the following connection details:

- Hostname: localhost
- Port: 3306
- Username: root
- Password: root


