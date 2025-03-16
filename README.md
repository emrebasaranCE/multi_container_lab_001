## Multi Container Lab 001

In this example, we will containeraze 3 different apps which these are: backend, frontend and database.

1) Creating MongoDB:

        docker run -d --rm \
            -p 27017:27017 \
            --name mongodb \
            --network new_network \
            mongo


