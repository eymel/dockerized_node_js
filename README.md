# dockerized_node_js

# For development
- docker build -t nodebackend .
- docker run --rm   -p 9060:8080 -v `pwd -W`:/home/node/app -v node_modules:/home/node/app/node_modules --name myNodeServer  nodebackend 