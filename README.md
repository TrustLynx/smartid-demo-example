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
- import repository file **Smart-ID DEMO signing example.postman_collection.json** into your Postman instance:
![image](https://github.com/user-attachments/assets/dd294616-f8ec-48d5-a52e-66c043e29336)
- setup 01. Create Document request:
-- select file to put in a file field. In this example let`s use simple PDF file.
