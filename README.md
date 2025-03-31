# 🌩️ Real-Time Weather Streaming with Kafka, Flink, and PostgreSQL

This project demonstrates a real-time data streaming pipeline using Apache Kafka, Apache Flink, and PostgreSQL — all containerized with Docker. A Python Kafka producer generates fake `(city, temperature)` data and pushes it to a Kafka topic. Flink consumes the stream, calculates the average temperature per city over a 60-second window, and writes the results to a PostgreSQL table named `weather`. The setup includes a custom Flink deserialization schema, a Python producer with wait-for-it.sh to ensure Kafka readiness, and an init.sql file to automatically create the database table when the container starts. You can run the entire system with `docker compose up --build` after placing all components in their respective folders and ensuring your `docker-compose.yml` properly mounts `init.sql` and builds both the producer and processor services. This setup is ideal for learning or prototyping end-to-end stream processing pipelines.
