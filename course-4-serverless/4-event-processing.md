# Section 4: Event Processing

- ***Presigned URL*** is a special URL pointing to an S3 bucket that can be used by anyone to upload/read an object. It can be used to access an S3 bucket even if it is private.

- WebSocket allows to implement bi-directional communication between a web application and a server. It can be especially useful for applications like:
  - Messaging Applications
  - Real-time Notifications
  - Real-time Dashboards

- SNS is a service to send messages to other services. It has two main concepts:
  - Publishers - publish messages
  - Subscribers - consume incoming messages
  - Publishers and subscribers communicate via topics as:
    - A publisher publish a message to a topic
    - A subscriber receives a message if it is subscribed to a topic
    - One topic can have many subscribers
    - Subscribers can use various protocols: Lambda, HTTP, email, SMS, etc.
