# ECG Health Monitoring System using ESP8266

## Overview

This repository contains the source code for an Electrocardiogram (ECG) health monitoring system implemented on the ESP8266 microcontroller. The system acquires ECG data from a sensor, classifies it using machine learning, and transmits the results to a designated server for further analysis.

## Project Components

- **ESP8266 Microcontroller**: Responsible for ECG data acquisition and transmission.
- **ECG Sensor**: Connected to the ESP8266's analog pin (A0), measures ECG values.
- **WiFi Module**: Enables the ESP8266 to connect to a WiFi network for data transmission.
- **Server**: Hosted at "http:/192.168.99.12:5000/post," handles incoming ECG data.

## Setup

### WiFi Configuration

Configure the WiFi credentials in the code:

```cpp
const char *ssid = "your_wifi_ssid";
const char *password = "your_wifi_password";
```

### Server Configuration

Set the server address:

```cpp
const char *serverAddress = "http:/192.168.99.12:5000/post";
```

### ECG Classification Thresholds

Adjust classification thresholds:

```cpp
const int normalThreshold = 600;  // Adjust as needed
const int lvhThreshold = 900;    // Adjust as needed
```

## Code Explanation

### `setup` Function

- Serial communication initialization for debugging.
- Establishes WiFi connection.

### `loop` Function

- Reads ECG data and classifies it using `classifyECG`.
- Constructs a data string and sends it to the server via HTTP POST.

### `classifyECG` Function

- Classifies ECG data into categories based on predefined thresholds.

## Note

The current code utilizes a placeholder classification (`int classification = 1;`) for demonstration purposes. Replace it with actual machine learning logic for accurate ECG classification.

## Dependencies

- ESP8266WiFi library
- ESP8266HTTPClient library

Ensure the required libraries are installed in the Arduino IDE.

## Customization

Feel free to adapt the code to your specific needs and integrate a machine learning model for improved ECG classification accuracy.

## Contributing

Contributions are welcome. For major changes, please open an issue first to discuss potential updates. Ensure to follow the coding standards and conventions.
