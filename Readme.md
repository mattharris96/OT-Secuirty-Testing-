# OT Secuirty Testing

This Repo is for developing an OT sec test bed and developing ways to monitor and defend against it as well as testing for sec standards such as 62443

There will be an OT plant, Historian and HMI, Monitoring, Network reality etc. 

## Architecture ##

- IT: Grafana, Wazuh dashboard
- DMZ: MQTT broker (Mosquitto), Zeek/Suricata sensors, Conpot (decoy)
- OT: OpenPLC runtime, Historian (InfluxDB)

OpenPLC is a fully open‑source IEC‑61131‑3 PLC runtime that runs on standard compute (and has maintained v3/v4 runtimes & containers). Conpot emulates ICS protocols (Modbus/TCP, S7, BACnet, IEC‑104, etc.), great for exercising detections safely. Mosquitto provides a light, standards‑compliant MQTT broker with an official container image. InfluxDB + Grafana gives you a common “historian + visualisation” pattern; both provide official compose docs. Zeek / Suricata lets you generate rich OT network telemetry and signatures in parallel, ideal for purple‑team drills. Wazuh (optional) is an open SIEM/EDR suite with documented Docker deployment (single‑node or clustered). 