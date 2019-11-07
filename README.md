# HPC Project

## Description

Encrypts the image using DES algorithm using parallel and distributed computation with the help of Docker Swarm.

## Requirements

- 2 machines running Ubuntu 18.04/16.04 OS
- Docker CE

## How to run

1. Build the docker image - `./setup-docker.sh`
2. Change SERVER_IP in `.env` file to your system's IP (can find via `ifconfig`)
3. Change hostname in line 17 and 41 of system to that of two machine's hostnames
4. Initialize docker swarm and create the network - `./create-network.sh`
5. Deploy the server using the command - `docker stack deploy -c docker-compose.yaml test`
6. See the logs of both services by using `docker logs -f <SERVICE_NAME>` command. Replace the service name with the container id found by running `docker ps`
7. Run the following command in the host PC - `curl 0.0.0.0:3000/encrypt`
8. You will be able to see the logs on the console, the encrypted image will be output to `/tmp/output.jpeg` path.
9. If you want to change the input image, simply replace `original.jpeg` with another image but with the same name, and repeat from step 1.

# Team Members

- Priyansh Jain 16BCE0979
- Harshit Choubey 16BCE0515
