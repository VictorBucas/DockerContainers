1-1 For which reason is it better to run the container with a flag -e to give the environment variables rather than put them directly in the Dockerfile?

It is easier to change these environment variables, also for exemple putting these environment variables in a env and not pushing it to github is better for security.

1-2 Why do we need a volume to be attached to our postgres container?

We need a volume to persist the database data outside the container, so that stopping or deleting the container does not erase our databases, tables, or records.

1-3 Document your database container essentials: commands and Dockerfile.

docker run -p 8888:5000 --net=app-network --name=postgre_db -v ./data:/var/lib/postgresql/data -d VictorB/postgre_db

This command allows us to run our postgre_db image on a specific network and stock the database information in the data folder

docker run -p "8090:8080" --net=app-network --name=adminer -d adminer

Runs adminer on the same network as our postgre_db, allows us to make requests from adminer on our database

Our Dockerfile specifies the environment we are using postgre/apline and authetification informations, it also executes the files in docker-entrypoint at launch
