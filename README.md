#Confluent Kafka Demo

Tech Stack: Python, Kafka, Docker, REST API, Confluent, node

This implementation, will create a Python application that publishes vehicle location longitude-latitude data to a Kafka topic. Next, will use Node.js to start a web server that acts as a consumer for the messages received from the Kafka application.

This demonstrates a REST interface defined in server.js
The producer and consumer can be launched by GET messages
Consumers must "poll" Kafka continuosly for events
otherwise they are considered dead
The files restConsumer.js and restProducer.js were used as the basis for myconsumer.js and myproducer.js

Apache Kafka opensource does not support a REST interface. However, Confluent does support a REST API and this makes it much easier to interact with Kafka's engine


1. Navigate to the kafka-docker folder inside the kafka_vehicle_location folder. In a Terminal window, run the following command to initialize your Kafka container:

docker-compose up

2. Open your browser and navigate to the following URL: http://localhost:9021. This is the Confluent Control Center, and it will allow you to check the status of the Kafka cluster that you spun up.

3. From the command prompt, run the following command to install the Kafka Python client:

pip install kafka-python

4. Run the code in the PublishVehicleCoordinates.py file to produce the longitude and latitude data.

5. In a Terminal window, run the following command to install the Kafka JavaScript library.

npm install node-rdkafka

6. In a Terminal window, navigate to the kafka_vehicle_location folder. Start the web page by running the following command:

node server.js

7. Navigate to http://localhost:5000. Your web page should be titled “Confluence Kafka REST” and have a button labeled “Consume Vehicle Coordinates”.

