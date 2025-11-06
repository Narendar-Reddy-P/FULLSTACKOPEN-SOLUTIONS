# New Note Diagram
```mermaid
sequenceDiagram
    participant Browser
    participant Server

    Browser->>Server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    Server-->>Browser: Page Redirect Request to Location: /exampleapp/notes
    Note right of Browser: The server adds new note in the data.json and requests Browser to redirect the page to new location

    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    Server-->>Browser: HTML document

    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    Server-->>Browser: the css file

    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    Server-->>Browser: the javascript file
    Note right of Browser: The browser starts executing the javascript code that fetches the JSON

    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    Server-->>Browser: the data.json file
    Note right of Browser: The browser executes the callback function that renders the notes
