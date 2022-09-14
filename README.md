https://docs.docker.com/get-started/02_our_app/

### Basic gyan:

-   what's a `dockerfile`?
    it's a file that has instructions for creating a _docker image_

-   what's a `docker image`?

    -   it's a read-only template with instructions for creating a _docker container_
    -   images are often based on other images for eg. you might build an image based on alpine linux or ubuntu
    -   often times `your image = base img + your app code + your app dependancies + env vars`

-   what's a `docker container`?
    -   it's a runnable instance of a docker image
    -   it's like to a remote machine, you can ssh into a container

<hr />

-   create a `Dockerfile` in your project. This contains instructions for creating a _docker image_
-   Next, create a _docker image_ `docker build -t todo-app .`
    -   `-t` tags the image, calling it `todo-app`
    -   `.` at the end specifies path to the Dockerfile
-   Next, create a _docker container_ and _start_ it `docker run -dp 3000:3000 todo-app`
    -   `-d` runs the container in a _detached_ mode (in the background)
    -   `-p` maps the host's port 3000 to the container's port 3000. Without this port mapping, we won't be able to access the app

### Commands

-   SSH'ing into docker container:

    -   `docker exec -it 4f9dc04b2cd1666ee5007b8f78b7b9f18dfc584cb61294054f32ebbf7523e879 /bin/sh`

-   Remove all unused docker images: `docker image prune`
-   Remove all unused containers: `docker container prune`

-   `COPY . .`: Copy everything from the docker context (directory where the Dockerfile is) into the docker container. Files mentioned on `.dockerignore` are ignored

Note:

-   Add `CMD tail -f /dev/null` so you can ssh into container without it stopping
