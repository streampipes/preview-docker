# StreamPipes

**Note: If you plan to run the docker-compose file directly without reading the really good [installation guide](https://docs.streampipes.org/quick_start/installation) first (;-)), replace the placeholders `### TODO ADD HOSTNAME HERE ###` in the compose file before starting.** 

StreamPipes enables flexible modeling of stream processing pipelines by providing a graphical modeling editor on top of existing stream processing frameworks.

It leverages non-technical users to quickly define and execute processing pipelines based on an easily extensible 
toolbox of data sources, data processors and data sinks.

Learn more about StreamPipes at [https://www.streampipes.org/](https://www.streampipes.org/)

Read the full documentation at [https://docs.streampipes.org](https://docs.streampipes.org)

### Getting Started

StreamPipes will be fully open source in early 2018.

Until then, you can try StreamPipes using our pre-built Docker images:

* Download the `docker-compose.yml` file from [https://www.github.com/streampipes/preview-docker](https://www.github.com/streampipes/preview-docker)
* Follow the installation guide at [https://docs.streampipes.org/quick_start/installation](https://docs.streampipes.org/quick_start/installation)
* Check the [tour](https://docs.streampipes.org/user_guide/features) and build your first pipeline!

A recent version of Docker and Docker-Compose is required.

**Contents of the `docker-compose` files**

* Backend. The StreamPipes Backend is the main component of the StreamPipes Framework. It contains the application 
logic to create and execute pipelines. Furthermore, it provides a REST-API that is used by other components for communication.      
* UI.  This service uses nginx and contains the UI of StreamPipes.
The UI can, for example, be used to import new pipeline elements, create new pipelines and manage the pipeline 
execution. The UI communicates with the backend via the REST interface.
* Consul. Consul is used to store configuration parameters of the backend service and processing elements.
It is further used for service discovery. Once a processing element container is started in the network, it is
automatically discovered via the service discovery feature of Consul.
* Apache Zookeeper. Apache Kafka and Apache Flink require zookeeper to manage their clusters.
* Apache Kafka. Kafka is used as the primary message broker. It is possible to use other brokers or even multiple 
message brokers in a single pipeline, but Kafka is the default. The communication between the processing elements in a pipeline is mostly done via Kafka.
* Apache ActiveMQ. ActiveMQ is another message broker which can be used in addition to Kafka. Currently, the main purpose is to provide
an endpoint for the websocket connections required by the real-time dashboard of the StreamPipes UI.
* Apache CouchDB. CouchDB is the main database for StreamPipes data that needs to be persisted such as pipelines, users and visualizations created in the dashboard.
* Apache Flink. This service sets up a sample flink cluster with one jobmanager and one taskmanager. Although this cluster can be used for testing, it is not recommended for production use.
* PE Examples Sources. Contains example data streams as described in [https://www.github.com/streampipes/examples-sources](https://www.github.com/streampipes/examples-sources)   
* PE Examples Flink. Contains example data processors and data sinks using the Apache Flink Wrapper as described in [https://www.github.com/streampipes/examples-flink](https://www.github.com/streampipes/examples-flink)   
* PE Examples JVM. Contains example data processors and data sinks running directly on the JVM as described in 
[https://www.github.com/streampipes/examples-jvm](https://www.github.com/streampipes/examples-jvm)   
                             
         
### Extending StreamPipes

You can easily add your own data streams, processors or sinks. 

Check our developer guide at [https://docs.streampipes.org/developer_guide/introduction](https://docs.streampipes.org/developer_guide/introduction)

### Feedback

We'd love to hear your feedback! Contact us at [mail.streampipes@gmail.com](mailto:mail.streampipes@gmail.com)

