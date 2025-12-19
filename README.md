# vitals-producer-anomaly-94

This project generates random vitals data with occasional anomalies and sends it to a Kafka topic.

## Usage

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Gautam0610/vitals-producer-anomaly-94.git
    cd vitals-producer-anomaly-94
    ```

2.  **Configure the environment variables:**
    Create a `.env` file based on the `.env` example and fill in the required values:
    ```
    OUTPUT_TOPIC=your_topic
    BOOTSTRAP_SERVERS=your_kafka_brokers
    SASL_USERNAME=your_username
    SASL_PASSWORD=your_password
    SECURITY_PROTOCOL=SASL_SSL
    SASL_MECHANISM=PLAIN
    INTERVAL_MS=1000 # Generation interval in milliseconds
    ```

3.  **Build and run the Docker container:**
    ```bash
    docker build -t vitals-producer .
    docker run --env-file .env vitals-producer
    ```

## Dependencies

*   Python 3.9
*   kafka-python
*   python-dotenv

## Anomaly Generation

The producer introduces anomalies by generating extremely high values for heart rate and breaths per minute with a 1% probability. All other vitals remain within realistic limits.
