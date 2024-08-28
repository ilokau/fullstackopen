sequenceDiagram
participant browser
participant server

Note right of browser: New note is written and save button clicked

browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
activate server
server-->>browser: 201 Created
deactivate server

Note right of browser: Redirect to notes page

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
activate server
server -->>browser: HTML document
deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
activate server
server-->>browser: the css file
deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/example/main.js
activate server
server-->>browser: Javascript file
deactivate server

Note right of browser: Javascript code fetching data JSON is executed

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
activate server
server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
deactivate server

Note right of browser: Callback function that renders notes is executed
