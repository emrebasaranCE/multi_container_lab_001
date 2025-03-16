## Multi Container Lab 001

In this example, we will containeraze 3 different apps which these are: backend, frontend and database.

1) Creating network for better communication:

        docker network create multi-container-network

2) Creating MongoDB:

        docker run -d --rm \
            -p 27017:27017 \
            --name mongodb \
            --network multi-container-network \
            mongo

3) Creating backend build:

        docker build -t backend-node .

4) Running backend image:

        docker run -d --rm \
            --name backend-cont \
            --network multi-container-network \
            -p 80:80 backend-node

5) Creating frontend build:

        docker build -t frontend-node .

6) Running frontend image:

        docker run -d --rm \
            --name frontend-cont \
            -p 3000:3000 frontend-node

