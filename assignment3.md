# Assignment 3 OPTION 2

## Goal

Run MQTT traffc

## Try to use AWS IoT but give up

### About AWS IoT

Message Broker for AWS IoT
| Protocol | Authentication           | Port | ALPN Protocol Name |
| -------- | ------------------------ | ---- | ------------------ |
| MQTT     | X.509 client certificate | 8883 | N/A                |
AWS IOT ONLY SUPPORT QoS Level 0 AND 1
Use [AWS IoT SDK for Python v2](https://github.com/aws/aws-iot-device-sdk-python-v2) for device to connect to AWS Iot Core

### Why give up

- AWS IoT MQTT always enables TLS Encryption so it's difficult to track latency of MQTT message by using Wireshark after try.
- In Wireshark, there is only info about the TLS packet. Even I can use packet length to find out those data packet, some problems will occur when there is packet loss.
- When there is packet loss sometimes publisher would send multiple temperature data in one TLS packet. So it's unavailable to test and evaluate MQTT latency through AWS IoT.

## Environment

### 1. MQTT Broker

Ubuntu 18.04 LTS ()
Domain Name: ec2-3-81-217-129.compute-1.amazonaws.com
IP: 3.81.217.129

### 2. MQTT Client 1 (Publisher)

Ubuntu 18.04 LTS Name: Client (Virtual Machine in Virtual Box 6.1)


Local IP behind NAT: 10.0.2.4

### 3. MQTT Client 2 (Subscriber)

Ubuntu 18.04 LTS Name: Server (Virtual Machine in Virtual Box 6.1)


Local IP behind NAT: 10.0.2.15

## Testing process

### Create 
