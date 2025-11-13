Build with below command
`docker buildx build -t rayyt:ws1.1_node24 .`

Run with below command and access with localhost:8080
`docker run -d -p 8080:5000 --name ws rayyt:ws1.1_node24`
