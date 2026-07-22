# Exercise 0.6: New note in Single Page App diagram

```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: The user writes a new note and clicks Save

    Note right of browser: spa.js catches the form submission and calls preventDefault(), stopping the page from reloading

    Note right of browser: JavaScript creates a note object containing the note content and current date

    Note right of browser: JavaScript adds the note to the local notes list, clears the input field, and redraws the notes

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server

    Note right of server: The request body contains the new note as JSON

    Note right of server: The server saves the new note

    server-->>browser: HTTP 201 Created
    deactivate server

    Note right of browser: The browser stays on the same page. There is no redirect or page reload.
```