# Containerize Flask and Vue.js wab app

## Prerequisites?
### Backend

- Python 3.9+
- Flask

### Frontend

- Node.js 14+
- npm or yarn

## Setup & Installation

### 1. Clone the Repository

Clone the repository from [https://github.com/hostspaceng/community-challenge](https://https://github.com/paularinzee/Containerize-Flask-and-Vue.js-web-Microservice).

### build the image and run the container in detached mode
    ```sh 
    docker build -t web:latest .
    docker run -d --name flask-vue -e "PORT=8765" -p 8007:8765 web:latest
    ```

If all went well, then we should see this variable in the default.conf file within the running container:
    $ docker exec flask-vue cat ../etc/nginx/conf.d/default.conf


Ensure Nginx is listening on port 8765: listen 8765;. Also, ensure the app is running at http://localhost:8007 in your browser.

### To stop and remove the running container
    ```sh 
    docker stop flask-vue
    docker rm flask-vue
    ```
