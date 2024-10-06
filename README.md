The Smart Energy Management System is a versatile IoT solution designed to monitor, manage, and optimize energy usage in real time. This system is built using an ESP32 microcontroller, energy monitoring sensors, and an LCD display, with integrated cloud capabilities via the Blynk platform. The project aims to provide users with accessible and detailed insights into their energy consumption patterns, ultimately empowering them to make more informed decisions to enhance efficiency and reduce energy costs.

Features

	•	Accurate Energy Monitoring: This system utilizes the EmonLib library for precise voltage and current measurements. The energy consumption metrics, including Voltage (Vrms), Current (Irms), Power (Watts), and cumulative Energy Consumption (kWh), are calculated and displayed on an LCD.
	•	Cloud-Based Data Visualization: Data collected by the system is transmitted to the Blynk cloud platform, enabling users to access real-time energy usage statistics remotely via the Blynk mobile app. This feature allows for monitoring and analysis from anywhere, facilitating proactive energy management.
	•	Persistent Data Storage: Energy data is saved to the ESP32’s EEPROM, ensuring that historical consumption records are retained even during power outages. Upon reboot, the system reloads the stored data, allowing seamless continuation of energy tracking.
	•	User-Friendly Interface: An LCD display is integrated into the setup, showing real-time energy metrics directly on the device. This feature provides an instant view of energy usage without needing a mobile device.
	•	Adjustable Calibration: The system allows for the adjustment of voltage and current calibration factors, ensuring accuracy across different installation settings.

System Components

The Smart Energy Management System requires the following components:

	•	ESP32 Microcontroller: Acts as the brain of the system, handling data processing, cloud communication, and storage.
	•	CT Sensor for Current Measurement: This sensor captures real-time current flow, providing essential data for power calculations.
	•	LCD Display (I2C): Presents voltage, current, and power readings directly to the user.
	•	Blynk IoT Platform: Enables remote data access and visualization through a mobile app, which enhances the usability and accessibility of the system.
	•	EEPROM: Stores energy consumption data to ensure continuity and reliability over time.

How It Works

The system operates by continuously monitoring voltage and current, using these values to calculate apparent power and energy consumption in kilowatt-hours (kWh). Every few seconds, the latest energy metrics are calculated and sent to the Blynk platform for cloud storage and visualization. Simultaneously, these values are displayed on an LCD screen and stored in the EEPROM for data retention.

Key Functions

	•	sendEnergyDataToBlynk(): Responsible for calculating and updating the energy usage metrics. This function calculates the cumulative energy consumed, displays it on the LCD, and sends it to the Blynk app for remote access. It also saves the latest data to EEPROM for persistence.
	•	readEnergyDataFromEEPROM(): Reads stored kWh values from the EEPROM, which allows the system to resume accurate monitoring after a power cycle.
	•	saveEnergyDataToEEPROM(): Saves the current kWh value to EEPROM to ensure data is not lost during unexpected power outages. The function commits changes to memory, ensuring accurate data storage.

Setup and Installation

To deploy the Smart Energy Management System:

	1.	Hardware Setup: Assemble the components, connecting the CT sensor and LCD to the ESP32 as per the circuit diagram.
	2.	Configure the Code: Replace the placeholders for WiFi credentials and Blynk authentication token in the code with your own details.
	3.	Upload the Code: Use the Arduino IDE to upload the program to the ESP32. Ensure the necessary libraries (EmonLib, Blynk, EEPROM, etc.) are installed.
	4.	Calibrate the System: If necessary, adjust the calibration factors for voltage and current to match your sensor specifications.
	5.	Monitor and Analyze: Once deployed, you can view real-time energy data on the LCD and remotely access detailed statistics through the Blynk mobile app.

Benefits

	•	Cost Savings: By closely monitoring energy usage, users can identify trends and areas of inefficiency, helping to reduce unnecessary energy expenditure.
	•	Increased Sustainability: Promotes energy conservation efforts by raising awareness of real-time consumption, encouraging sustainable practices.
	•	Convenient Monitoring: The integration with Blynk provides a seamless way to view energy metrics on the go, supporting informed decision-making.
	•	Data Resilience: EEPROM storage ensures that energy data is preserved across sessions, making the system reliable for long-term usage.

Future Improvements

While the current setup is robust and functional, there are opportunities for future enhancements:

	•	Enhanced Data Analysis: Implementing trend analysis and historical data visualization can offer more in-depth insights into consumption patterns.
	•	Smart Alerts: Adding threshold-based alerts on the Blynk platform can notify users when energy usage exceeds certain levels.
	•	Multi-Sensor Support: Expanding to support multiple sensors can provide a more comprehensive view of energy consumption across different circuits or appliances.

Conclusion

The Smart Energy Management System is an effective solution for individuals and businesses aiming to gain control over their energy consumption. By leveraging IoT technology, this system not only provides real-time insights but also enhances data reliability and accessibility, making it a valuable tool for sustainable energy management.
