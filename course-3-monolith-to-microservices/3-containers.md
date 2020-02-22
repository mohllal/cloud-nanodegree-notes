# Section 3: Containers

- Docker is a tool that helps to create ***images***. An *image* (or Docker image) is a portable package that contains the application and its dependencies. An *image* can be used to instantiate multiple ***containers***.

- OS level virtualization allows us to run multiple isolated user-space instances in parallel. A ***container*** (or Docker container) is the isolated user-space instance that has the application code, the required dependencies, and the necessary runtime environment to run the application.

- Benefit of containers:
  - Docker images make it easier for developers to create, deploy, and run applications on different hardware and platforms, quickly and easily. Docker has become an essential tool in CI/CD pipeline nowadays.
  - Containers share a single kernel and share application libraries.
  - Containers cause a lower system overhead as compared to Virtual Machines.
  - Containers are platform independent.
  - Containers are easy to manage as compared to Virtual Machines (VMs).

- A Dockerfile is a text document which contains all the commands a user can call on the command line to assemble an image. Using `docker build` command, users can create an automated build that executes several command-line instructions in succession.

- The reverse-proxy server lies behind the firewall in a private network. The following are benefits of using a reverse-proxy server:
  - It raises the security level for accessing the services only through the reverse-proxy server (encapsulation of services).
  - It resolves the conflict between services running on the same port number in separate containers by directing the client requests to the appropriate backend server.

- By default NGINX buffers responses from proxied servers. A response is stored in the internal buffers and is not sent to the client until the whole response is received. Buffering helps to optimize performance with slow clients, which can waste proxied server time if the response is passed from NGINX to the client synchronously. However, when buffering is enabled NGINX allows the proxied server to process responses quickly, while NGINX stores the responses for as much time as the clients need to download them.

- Containers and virtual machines have similar resource isolation and allocation benefits, but function differently because containers virtualize the operating system instead of hardware. Containers are more portable and efficient.