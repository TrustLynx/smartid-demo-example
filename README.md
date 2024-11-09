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

  In current example **localhost:88** is Archive Service and **localhost:86** is Container Service ports.
- setup and run 01. Create Document request:
      ![image](https://github.com/user-attachments/assets/b97b68b1-3375-40e2-b7f2-db982436974d)
    - select file to put in a "file" field. In this example let`s use simple PDF file.
    - field "documentData" should have static value:
      ```
      {
      "objectName": "testObject",
      "contentType": "application/pdf",
      "documentType": "DMSSDoc",
      "documentFilename": "test.txt"
      }
      ```
   - run request and recieve document id from response:
     ![image](https://github.com/user-attachments/assets/e51f0af5-5f3b-432d-a292-0e5546717f90)
- setup and run 02. Initiate SmartID DEMO Signing request
  ![image](https://github.com/user-attachments/assets/968a326c-9f1f-4960-aa08-d396b37c2b85)
  In API URL you see document id from request 01: /api/signing/smart/pdf/[DOCUMENT_ID_FROM_REQUEST_01]/sign.
  Keep body JSON as it is as soon as it has DEMO id code for LV and LV is used as a country so no changes are needed.
  ```
  {
    "country": "LV",
    "idCode": "030303-10012"  
  }  
  ```
  Run request and recieve similar response (during the process SK ID Solutions DEMO services has simulated entering PIN code and prepared the response):
  ![image](https://github.com/user-attachments/assets/981ff075-154f-4b8b-a13d-7f9c28b33930)
  
  Copy "sessionCode" value to be used in next request
- setup and run 03. Get Signing Status request
  ![image](https://github.com/user-attachments/assets/054daeb6-00a9-41f2-831b-45e5e887f4a4)
  
  Put "sessionCode" value into API URL: api/signing/smart/session/[PUT_SESSION_CODE_HERE]/status
  Run request and recieve response:
  ![image](https://github.com/user-attachments/assets/4f8503e4-eaf7-4b61-8a1a-58c91abd45e3)
  
  Such response means document was signed with DEMO Smart-ID signature.
- setup and run 04. Download Signed document
  ![image](https://github.com/user-attachments/assets/3269eb2e-8e3f-41e6-8d16-0018761ee4fe)
  
  Put document id from request 01. to API URL: /api/document/[PUT_DOCUMENT_ID_HERE]/download. As a result signed document is downloaded:
  ![image](https://github.com/user-attachments/assets/f0786974-cd56-439f-a679-8ad1a5380e53)




  

