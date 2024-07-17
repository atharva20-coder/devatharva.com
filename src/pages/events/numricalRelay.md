---
title: Cybergrid Gaurdian - Numerical Relay
slug: cybergrid-gaurdian
date: 2023-12-15
author: Atharva Joshi
read_time: 6
tags: ["Java", "MySQL", "Embedded C", "Arduino", "Microcontroller", "ESP32"]
order: 2
draft: false
past: false
emoji: "⚡"
---

The CyberGrid Guardian project aims to enhance the implementation and simulation of distance protection algorithms using Java, addressing the limitations of assembly language currently employed in this domain. Java provides several advantages, including smoother and more efficient processes, reduced time consumption, and quicker fault detection, ultimately leading to better equipment protection. This project contributes valuable research by exploring Java-based distance protection algorithms and their practical application.

### Software Features 🌟

CyberGrid Guardian is a comprehensive numerical relay system designed for real-time fault detection in power transmission systems. Key features include:

1. **Real-time Fault Detection:** 🚨 The software supports sophisticated fault detection techniques like the Mann-Morrison and Three Sample methods, allowing users to switch techniques based on system conditions.
2. **Graphical User Interface (GUI):** 💻 An interactive and user-friendly interface facilitates easy navigation and control, enabling users to select fault detection techniques and customize the system.
3. **Relay Selection:** ⚡ Users can choose between Overvoltage and Overcurrent Relays, ensuring adaptability to diverse network requirements.
4. **Graphical Data Visualization:** 📊 The software provides graphical representations of relay data for quick performance interpretation and anomaly detection.
5. **CSV Data Analysis:** 📈 Supports data analysis through CSV file uploads, enhancing data management and usability.
6. **SQL Database Integration:** 🗃️ Stores comprehensive data, including real-time voltage and current measurements, fault detection results, and fault cause and timing.
7. **Real-Time Data Processing:** ⏱️ Operates on real-time data from microcontroller-based hardware, ensuring prompt fault detection and system protection.

### Interface 💻

![blue_heading](https://github.com/atharva20-coder/cyberGrid/assets/69634375/525b0508-60f1-48d6-8f93-40e26f5151b6)
![p1](https://github.com/atharva20-coder/cyberGrid/assets/69634375/5242963f-185b-43f1-a327-4f6b36c4da5d)
![p2](https://github.com/atharva20-coder/cyberGrid/assets/69634375/27d316f2-1ab0-420a-bc78-0d9ecb335ddb)
![p3](https://github.com/atharva20-coder/cyberGrid/assets/69634375/a88585e9-82b7-4f61-8197-355455105aea)
![p4](https://github.com/atharva20-coder/cyberGrid/assets/69634375/fc4c28ee-6fbb-4663-8ec6-313a4ac842da)
![p5](https://github.com/atharva20-coder/cyberGrid/assets/69634375/dc3dce40-7ae0-4474-a2cb-bd3ff00e8c3d)
![p6](https://github.com/atharva20-coder/cyberGrid/assets/69634375/64af53af-b0c7-41e4-a6ff-bfde3a69fc2f)

<div>
        <video controls width="800" autoplay muted>
            <source src="/src/images/posts/project-imgs/project.mp4" type="video/mp4">
        </video>
</div>

### Hardware Implementation ⚙️

![20231030_134648](https://github.com/user-attachments/assets/edf5ef0b-743f-4cfc-b059-5505c3b376e6)

The project also involves implementing the distance protection algorithms on hardware. The hardware setup includes:

- **Arduino Uno:** 🛠️ A versatile microcontroller board used for interfacing with sensors, motors, and other components.
- **Atmega 32a Microcontroller:** 🏿 A high-performance microcontroller with features suitable for complex algorithm implementation.
- **Potential Transformers:** ⚡ Used to measure high alternating voltage in power systems.
- **Current Transformers:** 🔌 Measure current and maintain an accurate ratio between primary and secondary circuits.
- **Signal Conditioning Unit:** 📡 Modifies raw analog signals from sensors for compatibility with monitoring and control devices.
- **Load:** 💡 Ensures circuit functionality by providing a necessary component for electricity utilization.

The Arduino IDE is used for real-time data accumulation, with data streamed via a serial cable and processed using Java. The Mann Morrison Algorithm is applied, and the simulation outputs values for resistance (R), capacitance (X), inductance (L), and impedance (Z). The algorithm, initially simulated for a single phase, can be extended to three phases by processing the voltage and current values of all three phases.

### Data Collection and Integration with Google Sheets

To enhance real-time monitoring and data analysis, the ESP32 microcontroller is programmed to read sensor data periodically and format it into CSV. The steps for Google Sheets integration include:

- **Google Developer Console:** 🌐 Create a project and enable the Google Sheets API.
- **OAuth 2.0 Authentication:** 🔐 Set up authentication to allow ESP32 access to the Google Sheets API.
- **Spreadsheet Access:** 📑 Share the target Google Spreadsheet with the Google Service Account email.

The ESP32 sends POST requests to Google Sheets using the API key and OAuth 2.0 authentication, appending formatted data to the spreadsheet at predefined intervals.

### Applications

- **Real-Time Monitoring:** 📡 Provides constant monitoring and immediate data access, crucial for various applications.
- **Remote Data Collection:** 🌍 Uses ESP32's Wi-Fi capabilities to collect data from remote locations and transmit it centrally.
- **Data Analysis:** 📊 Google Sheets' tools enable easy analysis, visualization, and sharing of collected data, useful for environmental monitoring, industrial automation, and more.

<div style="display: flex; flex-wrap: wrap; gap: 10px;">

<div style="flex: 1; min-width: 150px; border: 1px solid #ddd; border-radius: 5px; padding: 10px; text-align: center;">
  <a href="https://github.com/atharva20-coder/Solalign" target="_blank" style="display: flex; align-items: center; justify-content: center;">
    <svg height="24" width="24" viewBox="0 0 16 16" version="1.1" aria-hidden="true" style="fill: #000; margin-right: 5px;">
      <path fill-rule="evenodd" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.45.55.38A8.013 8.013 0 0 0 16 8c0-4.42-3.58-8-8-8z"></path>
    </svg>
    GitHub Repository
  </a>
</div>

<div style="flex: 1; min-width: 150px; border: 1px solid #ddd; border-radius: 5px; padding: 10px; text-align: center;">
  <a href="https://github.com/atharva20-coder/Solalign/blob/master/SolAlign.apk" target="_blank">📥 Download APK</a>
</div>
</div>

<br>

---

CyberGrid Guardian offers a robust solution for real-time fault detection and system protection in power transmission. By leveraging Java for algorithm implementation and integrating hardware and cloud-based data management, this project significantly enhances the efficiency and accuracy of distance protection algorithms.
