# PAO – PowerOfThree

It started with three people, less than one month, and one big idea:  
to bring together **Bare Metal, Embedded Linux, and Android Automotive** into a single connected system.

This project is the harvest of 9 months at the ITI Embedded Systems Track.  
That’s how **PAO – The Power of Three** was born.

- **The Power of Three People**: Patrick Atef, Abdallah, and Omar.  
- **The Power of Three Systems**: Bare Metal + Yocto + AOSP.  

Together, we designed, coded, and integrated everything end-to-end into a **Tri-System Embedded Architecture** that bridges microcontrollers, embedded Linux, and Android Automotive into a secure, intelligent automotive platform.

---

##  System Architecture

### 1. Bare Metal Microcontrollers
- **ESP32** → Secure fingerprint enrollment & authentication (SHA hashing).  
- **STM32 Bluepill** → Reads potentiometers & push buttons, transmits real-time data via CAN.  

### 2. Embedded Linux (Yocto on Raspberry Pi 3B+)
- Custom **Yocto layer (meta-pao)** with integrated **vsomeip**.  
- **Qt6 cluster UI** shows STM32 sensor data (CAN) & ESP32 fingerprint events (UART).  
- **systemd services** auto-launch the Qt6 app at startup.  
- Acts as the **central bridge node** between Bare Metal and Android Automotive.  

### 3. AOSP (Android Automotive on Raspberry Pi 5 – 16 GB RAM)
- Customized **AOSP 15** build with direct **VHAL integration**.  
- **vsomeip inside VHAL** → event-driven communication with Yocto.  
- **Kotlin Passenger App** with:  
  - HVAC multi-zone control  
  - Ambient lighting zones  
  - Media & music playback  
  - Voice assistant (Vosk)  
  - GPS navigation  
  - Secure OTA updates (SHA verification)  
  - Child Mode → multi-user profiles via OpenCV face detection  

---

##  Key Innovations
- **End-to-End Security** → Fingerprint & OTA updates protected with SHA hashing.  
- **vsomeip in Yocto & Android VHAL** → Event-driven communication across systems.  
- **meta-pao Yocto Layer** → Customized integration layer with automation (systemd).  
- **Qt6 Cluster UI** → Real-time visualization of CAN data.  
- **Immersive Android Automotive Passenger App** → Multi-zone HVAC, lighting, music, GPS & voice.  

---

## 📸 Passenger Display Screenshots

### Main Dashboard
<img src="photos/main1.png" width="400"> <img src="photos/main2.png" width="400">

### Ambient Lighting
<img src="photos/light1.png" width="300"> <img src="photos/light2.png" width="300"> <img src="photos/light3.png" width="300">

### HVAC Control
<img src="photos/hvac1.png" width="300"> <img src="photos/hvac2.png" width="300"> <img src="photos/hvac3.png" width="300">

### Navigation
<img src="photos/map1.png" width="300"> <img src="photos/map2.png" width="300"> <img src="photos/map3.png" width="300">

### Voice Recognition
<img src="photos/voice.png" width="400">

---

## Repositories

Our ecosystem is split into multiple repos:

- [**AOSP**](../AOSP) → Platform customization, VHAL, Kotlin passenger app.  
- [**Qt**](../Qt) → Cluster display with Qt6 & QML.  
- [**Bare-Metal**](../Bare-Metal) → STM32 & ESP32 drivers and secure fingerprint.  
- [**Yocto**](../Yocto) → Custom meta-pao layer with vsomeip and Qt integration.  
- [**OTA**](../OTA) → Secure update mechanism with SHA verification.  
- [**Security**](../Security) → Cryptography & communication security.  
- [**vsomeip**](../vsomeip) → Middleware for client/server communication.  
- [**.github**](../.github) → Org-wide configs and workflows.  

---

##  Vision

Three people.  
Three systems.  
One connected automotive platform.  

This is **PAO – PowerOfThree**.  
