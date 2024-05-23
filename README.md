HARDWARE REQUIREMENTS
COMPONENTS         SPECIFICATION
PROCESSOR          Intel Core i5
RAM                8 GB RAM
GPU                NVIDIA GeForce GTX 1650
MONITOR            15” COLOR
HARD DISK          512 GB
PROCESSOR SPEED    MINIMUM 1.1 GHz
NodeMCU            ESP8266EX
SOLENOID LOCK      12V DC
POWER SUPPLY       5V DC
RELAY              Electromechanical 5V DC
LCD                50mm x 20mm

SOFTWARE REQUIREMENTS
The software requirements document is the specifications of the system. It should include both a definition and a specification of requirements. It is a set of what the system should rather be doing than focus on how it should be done. The software requirements provide a basis for creating the software requirements specification. It is useful in estimating the cost, planning team activities, performing tasks, tracking the team, and tracking the team’s progress throughout the development activity. ARDUINO IDE, and Chrome would all be required.


CODE EXPLANATION
The Arduino code initializes with essential library inclusions based on the microcontroller in use (ESP32, ESP8266, or Arduino Raspberry Pi Pico W) to manage Wi-Fi and Firebase operations. It defines Wi-Fi credentials, Firebase API key, database URL, and user credentials necessary for Firebase authentication. A keypad is configured with a 4x4 matrix, where each key corresponds to specific characters, and a predefined password "1234" is set for user input validation. In the setup() function, the code initializes serial communication for debugging purposes and attempts to connect to the Wi-Fi network, providing connection feedback through the serial monitor. Upon successful connection, the program initializes Firebase with the provided credentials and sets a callback function for monitoring the token status. It also configures an output pin (D1) to control a lock mechanism. The loop() function continuously checks a specific path (/finger2/data) in the Firebase Realtime Database for a string value. If the value is "1", the program triggers the lock by setting the D1 pin high, waits for 1.5 seconds, and then sets the pin low, mimicking a lock/unlock action. After performing the action, it updates the Firebase database by setting the value to "2" to signal that the action has been completed. This loop ensures that the lock state is controlled in real-time based on the data received from Firebase, integrating hardware control with cloud-based data management.
