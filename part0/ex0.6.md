## Exercise 0.6 — New note in SPA

```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: User types a note and clicks Save

    Note right of browser: JS intercepts the event — no page reload

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    Note right of browser: Sends JSON: { "content": "...", "date": "..." }
    activate server
    server-->>browser: 201 Created { "message": "note created" }
    deactivate server

    Note right of browser: JS appends new note to the list and re-renders — no redirect
```
