# Open Systems Administration Activity (ASA) - Web server implementation

# What to do:

Public repository on github (asa-web)
Implement the web structure with 01 reverse proxy and 02 application servers
Implement the structure with 01 primary DNS server with direct resolution zone
Composed of the student's first name + .asa.br (Ex.: aristeu.asa.br)
Container creation script (shell)
PPT presentation


# What to deliver:

Complete repository (Github)
Presentation (PDF)

# Commands to start the project:

The "./run.sh" command runs all other commands:
```bash
./run.sh
```
Other commands:
```
echo "Creating images..."
docker build -t c01 -f c01/Dockerfile c01/
docker build -t c02 -f c02/Dockerfile c02/

docker build -t proxy -f Dockerfile.proxy .
docker image ls

echo "Creating the network..."
docker network create -d bridge asa-net

echo "Creating containers..."
docker run -dp 8001:80 --name c01 c01
docker run -dp 8002:80 --name c02 c02
