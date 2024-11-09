# Smart-ID DEMO Signing example using TrustLynx services
## Installation instruction
- create working directory, in currect example let it be C:/dev/docuwere/
- put files from current repository into your working directory
- adjust paths in docker-compose.yml file in case if you working directory is different (replace C:/dev/docuwere/ to your working diectory inside docker-compose.yml).
- make sure your working environment has docker engine and docker compose plugin installed
- make sure your working environment allows outgoing connections
- navigate to working directory and run the command
  
  ```
  cd C:/dev/docuwere/
  docker-compose up -d
  ```
- docker will download necessary image versions and auto-start the containers
## Testing Smart-ID DEMO signing using Postman
