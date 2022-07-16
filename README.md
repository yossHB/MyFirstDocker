# MyFirstDocker
Get started with Docker Compose


Command used 

## Step 1: Setup

Define the application dependencies.
1. Create a directory for the project:
- mkdir composetest
- cd composetest
2. Create a file called app.py
3. Create file called requirements.txt

## Step 2: Create a Dockerfile
-  create a file named Dockerfile

## Step 4: Build and run your app with Compose
1. start up your application by running docker compose up.
2. Enter http://localhost:8000/ in a browser to see the application running.
3. Switch to another terminal window, and type docker image ls to list local images.
4. docker inspect <tag or id>
  - docker image ls
5. Stop the application
  - docker compose down
## Step 5: Edit the Compose file to add a bind mount
- Edit docker-compose.yml

## Step 6: Re-build and run the app with Compose
- docker compose up
  
## Step 7: Update the application
- Change the greeting in app.py
  
## Step 8: Experiment with some other commands
- to run your services in the background, you can pass the -d flag (for “detached” mode) to docker compose up.
  - docker compose up -d
- use docker compose ps to see what is currently running
  - docker compose ps
- to see what environment variables are available to the web service 
  - docker compose run web env
- stop your services
  - docker compose stop
- Pass --volumes to also remove the data volume used by the Redis container 
  - docker compose down --volumes
  
  
  
  
  
  
  
  
  
  
  
  
  
  
