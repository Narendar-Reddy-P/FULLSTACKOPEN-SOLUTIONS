# New note in Single page app diagram

```mermaid
sequenceDiagram

   participant User
   participant client
   participant server

   User->>client:User adds new note
   client->>client:Note gets updated on the data.json on client side
   client-->>User: New note is visible on the UI
   client->>server:POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
   Note right of client:request is sent to add new note in data.json file
   server-->>client:Status Code 201
   Note right of client: Informs client that note has been added
