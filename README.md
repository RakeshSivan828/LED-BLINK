# LED-BLINK
# 💡 Experiment 01 – Interfacing a Digital Output (LED) with ARM Development Board

### 🎯 **Aim**
To interface a digital output (LED) to an ARM development board and write a blink code.

---

### ⚙️ **Components Required**
- STM32CubeIDE  
- NUCLEO ARM Development Board  

---

### 🧠 **Theory**

**ARM (Advanced RISC Machine)** is a 32-bit processor architecture developed by ARM Holdings. It is widely used in embedded systems and SoC (System-on-Chip) products. Many semiconductor companies like Samsung, Atmel, and Texas Instruments license ARM architecture to design their own SoCs.
### 🧩 **What is an ARM7 Processor?**
The **ARM7 processor** is commonly used in embedded system applications. It provides a balance between the classic ARM architecture and the newer Cortex series, offering an excellent platform for both hardware and software development.
### 🔍 **LPC2148 Microcontroller**
The **LPC2148**, developed by NXP Semiconductors (Philips), is a 16/32-bit ARM7-based microcontroller featuring a wide range of peripherals.
#### **Key Features**
- 16/32-bit ARM7TDMI-S core in LQFP64 package  
- On-chip **Flash memory**: 32 KB – 512 KB  
- On-chip **SRAM**: 8 KB – 40 KB  
- **ISP/IAP** via on-chip bootloader  
- **Embedded ICE-RT** and **Real Monitor** for real-time debugging  
- **USB 2.0** full-speed device controller with 2 KB endpoint RAM  
- **10-bit ADC** (6 or 14 channels, 2.44 μs conversion time)  
- **10-bit DAC** for analog output  
- **Timers:** Two 32-bit timers, watchdog, and PWM unit  
- **RTC** with 32 kHz clock input  
- **UARTs (2x), I²C (2x)** up to 400 kbit/s  
- **5V-tolerant GPIOs**, 21 external interrupt pins  
- **Max CPU Clock:** 60 MHz using on-chip PLL (lock time 100 µs)  
- **Crystal Frequency:** 1 MHz – 25 MHz  
- **Power modes:** Idle and Power-down with peripheral clock scaling  

---

### 🧭 **Procedure**

1. Open **STM32CubeIDE**.
   <img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/5a9f5f74-79a5-40cd-b067-8541e0bb4bd2" />


2. Click **File → New STM32 Project**.
<img width="940" height="450" alt="image" src="https://github.com/user-attachments/assets/21abc0c5-c518-4a10-bff9-ac3b7b535588" />

<img width="980" height="450" alt="image" src="https://github.com/user-attachments/assets/edf33429-8eea-4857-a991-c2d7706fc787" />

3. Select the **target microcontroller** or board and click **Next**.
<img width="940" height="450" alt="image" src="https://github.com/user-attachments/assets/715ed546-1ee2-45a3-9e95-063d767a09ff" />

4. Name the project.
<img width="534" height="450" alt="image" src="https://github.com/user-attachments/assets/16abcf54-e534-4fd7-ade3-02e61ab9dc07" />

5. The corresponding `.ioc` file will be generated automatically.
<img width="940" height="450" alt="image" src="https://github.com/user-attachments/assets/e7cc2f85-3974-42f0-a998-9bf034b3795b" />


6. Configure the pins as **GPIO (Input/Output)**, **USART**, etc. as needed.
   <img width="920" height="450" alt="image" src="https://github.com/user-attachments/assets/930132ac-ce9e-48dd-a70a-a69cb99f8754" />

7. Save the configuration (`Ctrl + S`) – the base C program will be generated automatically.
  <img width="980" height="450" alt="image" src="https://github.com/user-attachments/assets/6d90005c-f236-43d5-aaa2-ae8682a5d204" />

 
8. Edit the generated main program as required.
  <img width="920" height="450" alt="image" src="https://github.com/user-attachments/assets/29269e2d-4686-4409-a115-dca5dcc31960" />

9. Click **Project → Build All**.
   <img width="920" height="450" alt="image" src="https://github.com/user-attachments/assets/979e8b12-00d7-4905-8d2d-81dd1f5859e1" />

10. Link the **HEX file** using the post-build process.
 <img width="721" height="450" alt="image" src="https://github.com/user-attachments/assets/ce012458-961d-45af-8aa9-e61133d20694" />

11. Click **Debug** and connect the **STM Nucleo Board**.
   <img width="920" height="450" alt="image" src="https://github.com/user-attachments/assets/de557816-81ea-41bf-8e43-f733a77ba09a" />

13. Click **Run** to execute the program.
    
---

### 💻 **Program**


```c
#include "main.h"

void SystemClock_Config(void);
static void MX_GPIO_Init(void);

int main(void)
{
    HAL_Init();
    SystemClock_Config();
    MX_GPIO_Init();

    while (1)
    {
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET);
        HAL_Delay(1000);
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);
        HAL_Delay(1000);
    }
}
```
---
### OUTPUT
CASE 1: LED ON

<img width="1280" height="576" alt="image" src="https://github.com/user-attachments/assets/5837757b-332b-487a-8820-10c96b5f31f0" />


CASE 2: LED OFF

<img width="1280" height="576" alt="image" src="https://github.com/user-attachments/assets/b9f673ed-de98-4519-bfea-a9081039cf79" />

---
### RESULT
Interfacing a digital output with ARM microcontroller is executed and the results are verified.
