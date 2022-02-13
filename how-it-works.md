Task 1. Serve html files in public.

- The task wants us to serve html file when a domain is accessed.
- In this case the domain is the localhost
- I copied the devops-intern-task directory which contains the public directory into /var/ww/html
- I then set the root to point to the public folder as seen in the nginx.conf file.
- I restarted the nginx server with `sudo service nginx restart` and tested on localhost.

Task 2: Port forward the server to the API.

- The api runs on localhost:3000/api
- I decided to reverse-proxy localhost/api to localhost:3000/api
- I set the server_name to localhost
- I set the location to /api
- I then set the proxy pass to http://localhost:3000/api (which is the line that performs the reverse proxy)
- I restarted the nginx server and tested the followiing endpoints on the server
  - http://localhost/api responded with a json object with message "Hello"
  - http://localhost/api/users responded with a json array consisting of a user objects.
