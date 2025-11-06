# New Note Diagram
```mermaid
sequenceDiagram
    participant Client
    participant Server

    Client->>Server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    Server-->>Client: Page Redirect Request to Location: /exampleapp/notes
    Note right of Client: The server adds new note in the data.json and requests client to redirect the page to new location

    Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    Server-->>Client: HTML document

    Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    Server-->>Client: the css file

    Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    Server-->>Client: the javascript file
    Note right of Client: The browser starts executing the javascript code that fetches the JSON

    Client->>Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    Server-->>Client: the data.json file
    Note right of Client: The browser executes the callback function that renders the notes
