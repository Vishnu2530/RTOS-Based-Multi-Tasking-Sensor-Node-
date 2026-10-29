RTOS-Based Multi-Tasking Sensor Node (STM32 + FreeRTOS)
An embedded system project demonstrating multi-tasking using FreeRTOS on an STM32 microcontroller.

The system simulates an IoT sensor node that reads environmental and motion data, processes it using RTOS tasks, and logs the results through UART.

This project demonstrates practical use of RTOS primitives such as tasks, queues, mutexes, and software timers.

System Architecture
Sensor Task ---> Queue ---> UART Logger Task | ---> Actuator Task (LED Control)

Software Timer (Watchdog Monitoring)

Key Features
FreeRTOS based multi-tasking system
Simulated sensors
Temperature
Humidity
Accelerometer (X, Y, Z)
Queue-based inter-task communication
Mutex protection for UART
Software Timer used as Watchdog
LED actuator triggered by motion detection
UART logging for debugging and monitoring
Tasks Implemented
Sensor Task
Simulates sensor readings periodically and pushes the data to a FreeRTOS Queue.

Generated data:

Temperature
Humidity
Accelerometer (X, Y, Z)
UART Logger Task
Receives data from the queue and prints formatted logs via UART.

Example output:

Temp: 25.00 C | Humidity: 58.00 % | AccelX: 0.32 | AccelY: -1.25 | AccelZ: 9.12

Actuator Task
Controls an LED depending on motion detected from accelerometer values.

Example:

Motion Detected -> LED ON
No Motion -> LED OFF

Watchdog Timer
A FreeRTOS Software Timer periodically prints system health status.

Example:

System Alive - Watchdog Timer

RTOS Concepts Demonstrated
This project demonstrates the following FreeRTOS primitives:

Task Creation
Queue Communication
Mutex Synchronization
Software Timers
Inter-task Communication
Shared Resource Protection
Hardware Platform
Target MCU: STM32F103C8T6 (Blue Pill)

Peripherals used:

UART1 (Logging)
GPIO (LED actuator)
I2C1 (Sensor interface ready)
Software Stack
STM32CubeIDE
STM32 HAL Drivers
FreeRTOS
CMSIS-RTOS v2 API
Project Folder Structure
Core/ ├── Inc └── Src

Drivers/

Middlewares/ └── FreeRTOS

RTOS_Multi_Tasking_Sensor_Node.ioc

Build Instructions
Open the project in STM32CubeIDE
Build the project
Flash firmware to the STM32 board
Open a Serial Terminal (115200 baud)
Example Output
Temp: 24.00 C | Humidity: 55.00 % | AccelX: -0.55 | AccelY: 1.20 | AccelZ: 9.03
Motion Detected -> LED ON
System Alive - Watchdog Timer

