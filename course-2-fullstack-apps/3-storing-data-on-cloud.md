# Section 3: Storing Data on the Cloud

- ***RAM (Random Access Memory)***: Data can be accessed quickly, but is erased once the server restarts. It may be okay to use RAM when prototyping, and later replace it with a persistent database.

- ***Hard Drive Disk***: Data remains after server restarts, but is specific to that server (not shared across servers).

- ***Race Condition***: When an application’s behaviour is dependent on other uncontrollable events. This is an issue with storing data on disks or RAM of multiple servers.

- ***Relational Database***: can store at scale, improve search runtime, and maintain relationships between data fields. We recommend using a database for storing data.

- ***SignedURLs*** allow clients to send and receive data by directly communicating with the file store. This saves the server from using its bandwidth to serve as the intermediary that transmits data to and from the client. This is faster for clients as well.

- ***CORS Cross Origin Resource Sharing***: defines how a client can interact with a resource, and what the client can and cannot do with that resource. Setting the CORS policy of our S3 bucket allows our client to communicate with the S3 bucket using the SignedURL pattern.

- ***IAM user role***: an IAM role can give a user a set of permissions to access one or more services.

- ***IAM service role***: an IAM role gives a service a set of permissions to access one or more services.
