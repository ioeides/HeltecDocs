# CubeCell Series Quick Start

## Summery

We belive [CubeCell Series](https://heltec.org/cubecell) is the best choose for LoRaWAN node applications, which provide following main features:

- **Fully Arduino-Compatible;**
- **Urtral low power design, best can reach 3.5uA in deep sleep mode (with RTC clock running);**
- **Low-cost;**
- **Integrated encryption algorithm, for example, a product based on CubeCell, if someone copied the frameware inside the flash and program into a clone hardware, it will not running;**
- **Use ASR650x, it's PSoC4000 and SX1262 inside one chip, makes application circuit has smaller size;**
- **Solar pannel support;**
- **LoRaWAN protocol support;**
- **AT command support;**
- **In the LoRaWAN relevant examples, have a reasonable timeline planning.**

``` Tip:: for example, an application need send data to server every 10 minutes, then in a cycle, only ~1 second is in the state of sending, other 9 minutes and 59 seconds are in low sleep low power Consuming status.

```

## Install CubeCell relevant Framework

``` Tip:: Please confirm whether the USB driver, Git and Arduino IDE has been installed correctly.

```

*If not, please view this two articles [establish serial connection](https://heltec-automation-docs.readthedocs.io/en/user_manual/establish_serial_connection) and [Install Git and Arduino IDE](https://heltec-automation-docs.readthedocs.io/en/user_manual/how_to_install_git_and_arduino).*

there are two methods to install the CubeCell framework, choose one of them.

### Use Arduino board manager

Open Arduino IDE, and click `File`->`Peferences`->`Settings`

![](img/quick_start/01.png)

![](img/quick_start/02.png)

Input following json url to board manager URLs:

**Recommend:** [https://docs.heltec.cn/download/package_CubeCell_index.json](https://docs.heltec.cn/download/package_CubeCell_index.json)

or

**China main land:** [http://119.23.153.38/download/package_CubeCell_index.json](http://119.23.153.38/download/package_CubeCell_index.json)

![](img/quick_start/03.png)

Click `Tools`->`Board:`->`Boards Manager...`, search `Heltec cubecell`in the new pop-up dialog, select the latest `releases` and  click `install`

![](img/quick_start/04.png)

![](img/quick_start/05.png)

The source code of Heltec ASR650x series (ASR6501&ASR6502) framework available here: [https://github.com/HelTecAutomation/ASR650x-Arduino](https://github.com/HelTecAutomation/ASR650x-Arduino)

### Via Git

Please refer to this document: [Install CubeCell Frame via Git](https://github.com/HelTecAutomation/ASR650x-Arduino#installation-instructions)

&nbsp;


## Running an Example

Connect your CubeCell board to computer via a **high quality** Micro USB cable *(This is the most common reason we had encountered can’t program software)*. 

### Correctly Config the Tools Menu

In the tools menu, there are following options:

- **Board** -- Choose the right hardware connected to your computer;
- **LORAWAN_REGION** -- LoRaWAN protocol region definition, strictly follow [LoRaWAN 1.1 Regional Parameters](https://lora-alliance.org/sites/default/files/2018-04/lorawantm_regional_parameters_v1.1rb_-_final.pdf);
- **LORAWAN_CLASS** -- Now with Class A and Class C supported;
- **LORAWAN_NETMODE** -- OTAA or ABP;
- **LORAWAN_ADR** -- Turn ON or turn OFF ADR (Adaptive Data Rate);
- **LORAWAN_Net_Reservation** -- This is a feature outside the LoRaWAN protocol, only valid in OTAA mode. If this option is enabled, when system reset does not need join again. Projects such as smart street lights may be useful.
- **LORAWAN_AT_SUPPORT** -- AT command will provide many useful functions, for example, users can use serial port to config LoRa Node's DevEui, AppKey, or make node sleep, reset etc.
- **LORAWAN_RGB** -- RGB light for LoRaWAN status:
  - `Purple -- Join;`
  - `Blue -- First RX window;`
  - `Yellow -- Second RX window;`
  - `Green -- Join done.`
- **COM Port** -- Device's serial port in your computer.


``` Note:: **LORAWAN_Net_Reservation:** For example, a large-scale power outage in city, when power is restored, thousands of devices are connected to the network at the same time, which may cause the LoRa gateway or server to fail. Enable this feature will avoid this situation. Enable LORAWAN_Net_Reservation must disable Frame counter (fCnt) in LoRa server.

```

![](img/quick_start/06.png)

### Select an example

![](img/quick_start/07.png)

### Compile and upload

![](img/quick_start/08.png)



### New a sketch for CubeCell

In Arduino IDE, click `File --> new` and copy the following code:

```arduino
// the setup routine runs once when starts up
void setup(){

  // Initialize the Heltec ASR650x object


// the loop routine runs over and over again forever
void loop() {

}
```

## External resources

### Serial port cannot connected to Linux system?

In the Linux system, If encounter the serial port cannot be connected. Please refer to this document:
[https://playground.arduino.cc/Linux/All/#Permission](https://playground.arduino.cc/Linux/All/#Permission)

&nbsp;

Enjoy!
