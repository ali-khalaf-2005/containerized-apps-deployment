# Docker Networking Lab

## Objective
Learn how Docker containers communicate through bridge networks and how Docker's embedded DNS resolves container names.

## Environment
- Docker Engine
- Ubuntu containers
- User-defined bridge network

## Tasks Performed
- Created a custom bridge network named `app-net`.
- Connected existing containers to the custom network.
- Tested container-to-container communication using `ping`.
- Inspected network configuration, container IP addresses, and gateway.
- Disconnected a container from the network and observed the DNS resolution failure.
- Reconnected the container and verified communication again.

## Key Learnings
- Containers need a suitable shared network to communicate.
- User-defined bridge networks provide automatic DNS resolution by container name.
- Container IP addresses can be inspected using `docker network inspect`.
- DNS resolution failure and network connectivity failure are different issues.
- Network disconnection affects communication without deleting the container.

## Cleanup
Remove only the containers and networks created for this lab. Avoid broad cleanup commands such as `docker system prune` when unrelated Docker resources must be preserved.
