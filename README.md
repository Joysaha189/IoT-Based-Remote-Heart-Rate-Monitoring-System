# IoT-Based Remote Heart Rate Monitoring System

## Overview

This project presents an effective health monitoring system designed to support early detection of heart conditions using an **IoT-based ECG monitoring approach**. The system acquires ECG signals through a wearable sensing node, computes the heart rate, and transmits the processed data to the cloud via **Wi-Fi connectivity**.

---

## Hardware Components

- AD8232 ECG module  
- ESP8266 (NodeMCU)  
- Three disposable ECG electrode pads  
- Breadboard  
- Miscellaneous components (jumper wires, tape, etc.)

---

## System Architecture

![workflow_diagram](Images/workflow.png)

1. **Data Acquisition:**  
   The AD8232 ECG module collects physiological ECG signals from the body surface.

2. **Processing:**  
   A NodeMCU (ESP8266) samples the ECG signal at **100 samples per second**.

3. **BPM Calculation:**  
   Data is processed using **Arduino IDE or MATLAB** to detect R-peaks and compute the mean R–R interval.

4. **Transmission:**  
   The calculated heart rate is uploaded to **ThingSpeak** and backed up using **Gmail** and **Google Drive**.

---

## System Algorithm

- Acquire ECG data for approximately **3 seconds** at 100 samples/second  
- Detrend and normalize the signal to remove DC offset and baseline wander  
- Detect local maxima to identify **R-peaks**  
- Compute heart rate from the mean R–R interval  
- Upload BPM data to ThingSpeak  
- Repeat the process every **30 seconds**

---

## Emergency Protocol

![results](Images/outputs.png)

If the calculated heart rate is abnormal (**< 60 BPM or > 120 BPM**) for **five consecutive readings**:

- The system automatically records a longer **12-second ECG signal**  
- Generates a **CSV file** and a **plot of the ECG waveform**  
- Emails the data files to a physician for immediate review

---

## Project Status

✅ **Completed** — Baseline implementation  

🔧 **Open for enhancements and upgrades**

---

## Contributors

- Farhan Hamid  
- Subah Karnine  
- Sadia Afrose  
- Shafim Bin Hassan  
- **Joy Saha**  
- Ishtiaque Ahmed  
- Md Al Amin Patwary  

Department of Electrical & Electronic Engineering  
Bangladesh University of Engineering and Technology (BUET)

---

## License

This project is for **academic and educational purposes only**.
