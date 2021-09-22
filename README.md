# Whackamole - Reflex Measurement App

## How to install

- install Docker
- either clone the repo or download as zip
- open with IntelliJ as an SBT project

### How to start

- in a terminal window, navigate to the folder where this repo is downloaded and run `docker-compose up` to build and
  start the containers required to integrate kafka with Spark
    - if desirable, a console consumer for kafka can be created inside the docker container to view kafka records. Run
      the below commands in a new terminal window or tab.
      > ```bash
    > docker exec -it reflex-measurement-kafka bash
    > bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic whackamole
    > ```
- Run `src/main/scala/whackamoleServer` to start the Akka Http Server
- Run `src/main/scala/whackamoleSparkAggregator` to start Spark application that measures avg reflex time over clicks
- Navigate to `localhost:9998` and click the read square to send data to the back end :smiley:
- Results will appear in the console of the `whackamoleSparkAggregator`.

### For questions or suggestions

If you have changes to suggest to this repo, either

- submit a GitHub issue
- submit a pull request!

