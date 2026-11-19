# Power-Control-Monitoring-Board-
A custom designed board that monitors power usage, calculates SOC, and can be used to switch rails off in an emergency. 

## Architecture

# MCU 

The PCB is controlled by an ESP32 S3 DEVKIT. Functionality includes:
 - Fuel pump algorithm to estimate SOC real-time 
 - Monitoring abnormal current behavior
 - Isolating / rebooting failing components

# CANBUS

CANBUS will be the primary mode of communication with the rest of the robot. CANBUS is implemented through TWAI, which is then put through a chip to correct voltages. 

CANBUS lines are completely electrically isolated from the main power rails through an isolation transformed, meaning circuit can tolerate voltage surges +100V on the CANBUS lines without compromising circuitry. The chip itself lists 2.5kV, but I don't trust it. 
