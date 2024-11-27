# Homework Assignment on the Topic "Apache Kafka"

### [Solution (Screenshots of program execution explained) ](Solution_explined.md)

Today, you will focus on the practical application of Apache Kafka using the Python API, practicing the ability to create topics, write data to topics, and read data from them.

Imagine you work for a company that develops monitoring systems for the Internet of Things (IoT). The main task of the system is to collect data from various sensors installed in different buildings and analyze this data in real-time to track parameters such as temperature and humidity.

Apache Kafka is used as a messaging platform to efficiently transmit and process large volumes of data.

Your task is to implement several components of this system using Python and Apache Kafka, following the instructions below.

### Step-by-Step Instructions for Execution

### 1. Creating Topics in Kafka:

- Create three topics in Kafka:

> [!TIP]
> Add your names or other identifiers to the topic names to avoid duplication.

- `building_sensors` — to store data from all sensors.
- `temperature_alerts` — to store alerts for exceeding the permissible temperature level.
- `humidity_alerts` — to store alerts for exceeding or falling below the permissible humidity level.

### 2. Sending Data to Topics:

- Write a Python script that simulates the operation of a sensor and periodically sends randomly generated data (temperature and humidity) to the `building_sensors` topic.
- The data should contain the sensor ID, the timestamp, and the respective measurements.
- One execution of the script should correspond to a single sensor. That is, to simulate multiple sensors, you need to run the script multiple times. The sensor ID can be a random number, but it should remain consistent within one execution of the script. It may change when the script is executed again.
- Temperature: a random value between 25 and 45°C.
- Humidity: a random value between 15 and 85%.

Processing Data:

> [!TIP]
> This means that the sensor ID will be generated once when the script starts and should remain consistent for the entire execution of that script, but each time the script is executed again, a new random ID can be generated.

### 3. Data Processing:

- Write a Python script that subscribes to the building_sensors topic, reads the messages, and processes the data:

  - If the temperature exceeds 40°C, generate an alert and send it to the temperature_alerts topic.
  - If the humidity exceeds 80% or drops below 20%, generate an alert and send it to the humidity_alerts topic.
  - The alerts should include the sensor ID, the measured values, the timestamp, and a message indicating that the threshold has been exceeded.

### 4. Final Data:

- Write a Python script that subscribes to the temperature_alerts and humidity_alerts topics, reads the alerts, and prints the messages to the screen.
