## Project
String frequency manager - A SpringBoot application

### Objectives
Use JAVA Spring Boot to build an application with the following requirements -

Design and implement a small SaaS called String Frequency Manager.

The SFM shall process log files in a configurable local folder and keep track of how many times a particular string has appeared in those log files, called frequency of string. It shall also provide an API endpoint for the end user to make use of this frequency of string.

### About the log file
The log file for the String Frequency Manager is generated with each row of data in the following format:
{timestamp_in_epoch_millis}, {string}

Each row records the timestamp_in_epoch_millis whereby the string was generated in another system.

Upon the zero-th minute of every hour, a new log file that contains the data in the last hour will be generated and be placed into the same folder, the file name format is string-generation-{yyyymmddhh}.log
E.g. the file with name string-generation-2018093016.log is a file generated at 1600 hour on 30 Sep, 2018.

Construct the SaaS with the following requirements and constraints:
1. Load all available logs for the last 24 hours as stated above
2. A periodic logic flow that process new log files as stated above
3. Provide an API endpoint,
  - the caller can only send a string of up to 40 characters
  - The API shall return a json in this format: {“response”: “true|false”}
    If the string appears more than 5 times in the last 24 hours,
      ``` return {“response”: “false”} ```
    Else
      ``` return {“response”: “true”} ```
  - The API input is appended to the string of the URL as part of the GET parameter, in following way:
    > http://{domain_name}/isStringValid?string={string}
4. No special authentication is needed to the API endpoint, assuming that it will only be
called by another internal system located within the same network.

## Skills covered

- Java core (data structures, Collection API, etc)
- Java concurrency (threads, high level wrappers for dealing with thread pools, dead locks, race conditions, locks, etc)
- Spring core (dependency injection)
- REST API (http words, designing API endpoints, structuring JSON request/response objects)
- Networking (HTTP/HTTPS, TCP vs UDP, binary protocols (Protobuf))
- MySQL (using indexes, explain query, partitioning, complex joins, etc)
- AWS services (S3, Kinesis streams (similar to Kafka), Athena)
- Working with Docker containers
- Basic data structures (queue, stack, linked list, hash map)
- Basic algorithms (sort, search, traversing tree, etc)
- Optimising algorithms towards lower CPU/RAM usage, big O notation, etc
