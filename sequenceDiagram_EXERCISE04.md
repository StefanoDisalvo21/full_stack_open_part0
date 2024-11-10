sequenceDiagram
	participant Browser
	participant Server

	browser ->> server: POST https://studies.cs.helsinki.fi/exampleapp/new_notes
	server activate
	server ->> browser: Response Status Code “302”
	server  deactivate

	browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/notes
	server activate
	server ->> browser: HTML file
	server  deactivate

	browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
	server activate
	server ->> browser: css file
	server  deactivate

	browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
	server activate
	server ->> browser: all the content, including the new note
	server  deactivate
