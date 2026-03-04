# Network-Intrusion-Threat-Detector-
This project is a Network Intrusion Detection System (NIDS) designed to identify, log, and alert on malicious activity within a network. By analyzing traffic patterns and packet headers, the system distinguishes between legitimate user behavior and potential threats like DDoS attacks, port scanning, and SQL injections.    

🛡️ Network Intrusion Detection & Threat Analysis (NIDS)
📌 Project Overview
This repository contains a specialized Network Intrusion Detection System (NIDS). The goal is to monitor network traffic for suspicious activity and known threats, utilizing both signature-based detection and machine learning-driven anomaly detection.

In the modern cybersecurity landscape, identifying lateral movement and data exfiltration is critical. This project serves as a practical implementation of network security protocols and data-driven threat analysis.

🚀 Core Features
Packet Inspection: Real-time capture and analysis of TCP/UDP/ICMP packets.

Anomaly Detection Engine: A machine learning model (Random Forest/XGBoost) trained on the NSL-KDD or UNSW-NB15 datasets to identify "zero-day" threats.

Statistical Analysis: Calculates traffic flow metrics like packet frequency, duration, and payload size distributions.

Logging & Alerting: Generates structured JSON logs for integration with SIEM tools (like Splunk or ELK stack).

🛠️ Technical Architecture
The system operates through a structured four-phase pipeline:

Ingestion: Sniffing live traffic via Scapy or reading .pcap files.

Transformation: Engineering features such as source-destination entropy and flag counts.

Classification: Passing features through a trained classifier to label traffic as Normal, DoS, R2L, U2R, or Probing.

Reporting: Highlighting high-risk events in a terminal dashboard or log file.

📂 Repository Structure
Plaintext
├── data/               # Dataset samples (NSL-KDD / CSVs)
├── models/             # Pre-trained .pkl or .h5 models
├── notebooks/          # Exploratory Data Analysis (EDA) and Training
├── src/
│   ├── sniffer.py      # Packet capture logic
│   ├── preprocessor.py # Data cleaning and feature scaling
│   └── classifier.py   # Prediction engine
├── requirements.txt    # Python dependencies
└── main.py             # Main execution entry point
🔮 Future Enhancements
Deep Learning Integration: Implementing an LSTM (Long Short-Term Memory) network to better analyze sequential packet patterns over time.

Live Dashboard: Developing a web-based UI (using Streamlit) to visualize real-time traffic spikes and geographic IP mapping.

Automated Mitigation: Implementing an "Active Defense" feature that automatically updates local firewall rules (iptables) to block flagged IPs.

Encryption Inspection: Researching methods for behavioral analysis of encrypted (HTTPS/TLS) traffic without decryption. 
