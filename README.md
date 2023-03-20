# exercises-0.1-0.6
```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    browser->>server: [{"note":"Testing"}]

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "ddadaw", "date": ""2023-03-20T15:26:18.637Z"" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes
 ```
```mermaid
sequenceDiagram
    participant browser
    participant server

   browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "ddadaw", "date": ""2023-03-20T15:26:18.637Z"" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes
 ```
 
 ```mermaid
 sequenceDiagram
    participant browser
    participant server

browser-->server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
browser-->server: {"content": "test","date": "2023-03-20T20:13:42.131Z"}
activate server
server-->browser: {"message":"note created"}
deactivate server


Note right of browser: The browser rerender the page reflecting the newly added note
 ```
