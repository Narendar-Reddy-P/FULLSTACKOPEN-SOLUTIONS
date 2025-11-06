# New note in Single page app diagram

```mermaid
sequenceDiagram

   participant User
   participant Browser
   participant server

   User->>Browser:User adds new note
   Browser->>Browser:Note gets updated on the data.json on Browser
   Browser-->>User: New note is visible on the UI
   Browser->>server:POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
   Note right of Browser:request is sent to add new note in data.json file
   server-->>Browser:Status Code 201
   Note right of Browser: Informs Browser that note has been added
