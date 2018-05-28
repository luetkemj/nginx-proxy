# nginx-proxy with docker for a nodejs app

Build node app docker container:

`docker build -t foo/nodeapp node/.`

Run foo/nodeapp docker container in port 3000:

`docker run -d -p 3000:3000 --name node-app foo/nodeapp`

Navigate to [http://localhost:3000](http://localhost:3000) to test

Build nginx proxy docker container:

`docker build -t foo/nginx nginx/.`

Run foo/nginx docker container in port 8000 and proxy the running node-app container from port 3000:

`docker run -p 8000:80 --link node-app:app --name nginx-proxy foo/nginx`

Navigate to [http://localhost:8000](http://localhost:8000)
