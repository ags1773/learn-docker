https://docs.docker.com/get-started/02_our_app/

### Basic gyan:

-   create a `Dockerfile` in your project. This contains instructions for creating a _docker image_
-   Next, create a _docker image_ `docker build -t todo-app .`
    -   `-t` tags the image, calling it `todo-app`
    -   `.` at the end specifies path to the Dockerfile
-   Next, create a _docker container_ and _start_ it `docker run -dp 3000:3000 todo-app`
    -   `-d` runs the container in a _detached_ mode (in the background)
    -   `-p` maps the host's port 3000 to the container's port 3000. Without this port mapping, we won't be able to access the app
