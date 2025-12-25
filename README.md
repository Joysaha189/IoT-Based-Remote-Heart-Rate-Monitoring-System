# IoT-Based-Remote-Heart-Rate-Monitoring-System





#### **Overview**



This project presents an effective health monitoring system designed to detect heart conditions early through an IoT-based ECG monitoring method. The system collects ECG data via a wearable node, calculates the heart rate, and transmits it to the cloud using Wi-Fi.



#### **Hardware Components**



* AD8232 ECG Module
* ESP8266 (NodeMCU)
* 3 Disposable ECG Electrode Pads
* Breadboard
* Miscellaneous (Wires, Tape, etc.)



#### **System Architecture**

![workflow_diagram](Images/workflow.png)

1\. \*\*Data Acquisition:\*\* The AD8232 ECG module collects physiological data from the body surface.  

2\. \*\*Processing:\*\* A NodeMCU (ESP8266) collects data at a 100 samples/second sampling rate.  

3\. \*\*BPM Calculation:\*\* Data is processed in Arduino IDE or MATLAB to identify R-peaks and calculate the mean R-R interval.  

4\. \*\*Transmission:\*\* The processed heart rate is sent to ThingSpeak (IoT platform) and backed up via Gmail and Google Drive.



#### **System Algorithm**



\- Read data from AD8232 (~3 seconds at 100 samples/sec).  

\- Detrend and normalize the signal (remove DC offset/baseline wander).  

\- Find local maxima to identify R-peaks.  

\- Calculate Heart Rate from the mean R-R interval.  

\- Upload BPM to ThingSpeak.  

\- Repeat every 30 seconds.



#### **Emergency Protocol**


![results](Images/outputs.png)

If the calculated BPM is abnormal (<60 or >120) for five consecutive readings:  

\- The system automatically acquires a longer (12-second) ECG signal.  

\- Generates a CSV file and a plot graph of the data.  

\- Emails these files to a physician for immediate analysis.

#### Project Status



✅ Completed — Baseline implementation

🔧 Open for enhancements and upgrades

#### **Contributors**



Farhan Hamid, Subah Karnine, Sadia Afrose, Shafim Bin Hassan, Joy Saha, Ishtiaque Ahmed, and Md Al Amin Patwary  

Department of Electrical \& Electronic Engineering, Bangladesh University of Engineering and Technology (BUET)

#### **License**


This project is for academic and educational purposes.

