sequenceDiagram
	participant Browser
	participant Server


    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/spa.
	server activate
	server ->> browser: HTML file
    server deactivate
    
    browser ->> server: GET  https://studies.cs.helsinki.fi/exampleapp/main.css
	server activate
	server ->> browser: CSS File
    server deactivate
    
    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
	server activate
	server ->> browser: JavaScript File
    server deactivate
    

    browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
	server activate
	server ->> browser: raw data
    server deactivate

    browser ->> server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
	server activate
	server ->> browser: Response Status Code "201", with the "201" code the note is created and no more http request will be send, so the page will not reload.
	server  deactivate