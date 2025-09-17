# Kafka Java Example

## Prerequisites

- **Java JDK 8+** installed and added to your PATH
- **Gradle** (or use the provided `gradlew`/`gradlew.bat`)
- **Apache Kafka** downloaded and extracted to `C:\kafka` (its included in the project)
- **Kafka Broker and Zookeeper** running locally

## How to Start Kafka Broker and Zookeeper

Open two PowerShell windows:

**1. Start Zookeeper:**
```powershell
cd C:\kafka
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
```

**2. Start Kafka Broker:**
```powershell
cd C:\kafka
.\bin\windows\kafka-server-start.bat .\config\server.properties
```

## How to Run the Producer and Consumer

1. **Build the project:**
   ```powershell
   cd C:\Users\MSUSERSL123\IdeaProjects\Kafka
   .\gradlew build
   ```

2. **Run the Producer as a Java program:**
   ```powershell
   java -cp build\libs\Kafka-*.jar org.example.KafkaProducerExample
   ```

3. **Run the Consumer as a Java program:**
   ```powershell
   java -cp build\libs\Kafka-*.jar org.example.KafkaConsumerExample
   ```

## Notes
- Kafka broker and Zookeeper are not required externally; the project is self-contained with Kafka libraries.
- Make sure the Kafka topic used by producer/consumer exists, or create it in your code or via CLI if needed.
- Update the broker address in your Java code if not using the default `localhost:9092`.
- Check the `src/main/java/org/example/` directory for the producer and consumer Java files.
