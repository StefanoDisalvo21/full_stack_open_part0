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