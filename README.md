# ZOLC

This project serves as a preparation for the Best Hacking League hackathon.


# Setup

1. Install [Docker](https://www.docker.com/)
2. 
    Clone [backend](https://github.com/zolc/backend) and [frontend](https://github.com/zolc/frontend)
    repositories as subdirectories of this directory. The directory tree should look like this:
    ```
      docker-config
      ├───backend
      ├───frontend
      ├───nginx-config
      └───docker-compose.yml
    ```
3. Execute:
    ```
    $ docker-compose up -d
    ```
    while in the _docker-config_ directory.
    This command will build any missing images and run all the containers.
4. Access the application at [http://localhost:4200](http://localhost:4200). 
    The _/api/_ URL prefix redirect the request to the backend server
    stripping the _/api_ prefix in the meantime.


# General information

As _service name_ you should use:
* backend
* frontend
* app (for the nginx reverse proxy, shows all the traffic that gets to the server)
* database


## List of useful Docker commands:
* `docker-compose up -d` - starts all the containers in daemon mode (in the background).
* `docker-compose down` - stops all the containers.
* `docker-compose logs [service]` - shows the logs from all the containers.
    You may alternatively input the service name to see logs only from that service, this is optional.
* `docker ps` - shows running containers.
* `docker-compose exec [service] [command]` - run a command inside a docker container. 

  `docker-compose exec [service] bash` gives you shell access to that container.
* `docker-compose build [service]` - (re)builds the specified service's image (or images for all the services). Useful if you introduced any changes to files referenced in _Dockerfile_ or to the _Dockerfile_ itself.

  **IMPORTANT!**
  Generally you want to use `build` after changing the _requirements.txt_ file (for backend), because it means that new libraries should be downloaded.


## Database structure

See [database-diagram.png](database-diagram.png).



# Technologies we use

* Docker
* GraphQL
* Angular
* Python
* MongoDB
* Progressive Web Apps