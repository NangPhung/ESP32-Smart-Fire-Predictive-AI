# 🛡️ ESP32 Smart Fire & Smoke Predictive AI System

## Overview
This repository contains the architecture and core implementation of the **AI-Driven Predictive & Automated Emergency System**. Moving beyond traditional static-threshold fire and smoke warning systems, this project utilizes an ESP32 as a web server and MQTT client to stream real-time telemetry to a cloud-based Multi-Agent AI framework. 

The primary goal is to **predict** hardware failure and short-circuit risks hours before actual combustion occurs, effectively reducing false alarms and minimizing response latency.

## 🧠 Core Logic & Architecture
The system operates on a continuous, closed-loop **Multi-Agent Collaboration** model:

1. **Telemetry Agent:** Collects continuous time-series data (temperature, gas concentration via MQ2, and current draw) from the ESP32 nodes via MQTT. It parses and cleans the data stream to build context-rich prompts.
2. **Reasoning Agent (Long-chain reasoning):** The core analytic engine. It correlates minor fluctuations (e.g., a slow, abnormal rise in temperature coupled with a current spike) against historical component failure models. It calculates failure probabilities in real-time.
3. **Action Agent:** Upon receiving a high-risk diagnosis from the Reasoning Agent, it automatically generates JSON payloads to trigger hardware relays (e.g., cutting off the main power supply) and pushes a natural language diagnostic report to the Web Dashboard.

## 🚀 Current Status & Roadmap
* **Phase 1 (Completed):** Hardware integration, ESP32 web server deployment, sensor calibration, and real-time MQTT data streaming.
* **Phase 2 (In Progress - API Quota Required):** Full integration of the Long-chain Reasoning Agent. The system currently analyzes thousands of MQTT messages per hour, requiring significant continuous token throughput (~10M tokens/day) to maintain real-time predictive capabilities.

## 🛠️ Hardware & Tech Stack
* **Microcontroller:** ESP32 (configured as Web Server & MQTT Client)
* **Sensors:** MQ-Series (Gas/Smoke), NTC Thermistors/DHT (Temperature), ACS712 (Current)
* **Protocols:** MQTT, HTTP, WebSockets
* **AI Framework:** Custom Multi-Agent orchestration running Python

## ⚠️ Disclaimer
This system handles simulated emergency interventions. Do not deploy as the sole safety mechanism in critical life-support or industrial environments without professional certification.
