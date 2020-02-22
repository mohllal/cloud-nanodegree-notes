# Section 1: Best Practices for Microservices

> Microservices architectural style is an approach to developing a single application as a suite of small services, each running in its own process and communicating with lightweight mechanisms, often an HTTP resource API. These services are built around business capabilities and independently deployable by fully automated deployment machinery. There is a bare minimum of centralized management of these services, which may be written in different programming languages and use different data storage technologies.

- Benefits of Microservices:
  - Independent scaling.
  - Independent releases and deployments.
  - Independent development.
  - Decentralized governance.

- Microservices operational Concerns:
  - Service replication.
  - Service registration and discovery.
  - Service monitoring and logging.
  - Resiliency.
  - DevOps.

- Microservices architecture best fits for:
  - Two-pizza team / Cross functional.
  - Applications with high scalability needs.
  - Projects with high release velocity.

- Some important ***Docker Containers*** commands:
  - `create`— Create a container from an image.
  - `start`— Start an existing container.
  - `run`— Create a new container and start it.
  - `ps`— List running containers.
  - `inspect`— See lots of info about a container.
  - `logs`— Print logs.
  - `stop`— Gracefully stop a running container.
  - `kill` —Stop the main process in a container abruptly.

- Some important ***Docker Images*** commands:
  - `build`— Build an image.
  - `push`— Push an image to a remote registry.
  - `images`— List images.
  - `history`— See intermediate image info.
  - `inspect`— See lots of info about an image, including the layers.
  - `rm`— Delete an image.
  