# Single page app diagram

```mermaid
sequenceDiagram

   participant Browser
   participant server

   Browser->>server:GET https://studies.cs.helsinki.fi/exampleapp/spa 
   server-->>Browser: html document (spa)
   Note right of Browser:html page reload

   Browser->>server:GET https://studies.cs.helsinki.fi/exampleapp/main.css
   server-->>Browser: css file (main.css)
   Note right of Browser:CSS added to the page

   Browser->>server:GET https://studies.cs.helsinki.fi/exampleapp/spa.js
   server-->>Browser:the javascript file (spa.js)
   Note right of Browser: the javascript is run  and needs data.json to create note lists

   Browser->>server:GET https://studies.cs.helsinki.fi/exampleapp/data.json
   server-->>Browser:the json file (data.json)
   Note right of Browser: Notes are rendered on the page

