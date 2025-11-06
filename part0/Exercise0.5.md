#Single page app diagram

```mermaid
sequenceDiagram

   participant client
   participant server

   client->>server:GET https://studies.cs.helsinki.fi/exampleapp/spa 
   server-->>client: html document (spa)
   Note right of client:html page reload

   client->>server:GET https://studies.cs.helsinki.fi/exampleapp/main.css
   server-->>client: css file (main.css)
   Note right of client:CSS added to the page

   client->>server:GET https://studies.cs.helsinki.fi/exampleapp/spa.js
   server-->>client:the javascript file (spa.js)
   Note right of client: the javascript is run  and needs data.json to create note lists

   client->>server:GET https://studies.cs.helsinki.fi/exampleapp/data.json
   server-->>client:the json file (data.json)
   Note right of client: Notes are rendered on the page

