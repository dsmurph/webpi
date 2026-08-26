<div align="center">
  <img src="resources/webpi.png" alt="WebPi Logo" width="100">
</div>
<h3 align="center">The Hardware and Software Logic Framework</h3>
<br>
<div><h6><a href="NEWS.md">🔥🔥**NEWS**🔥🔥</a><h6><a href="README_DE.md">German version</a> | <a href="STORY.md">Story of WebPi</a></h6></div>

---

**🚀 The bridge between modern Linux and your hardware projects.**

WebPi is a lightweight C++ web interface framework for the Raspberry Pi. It was designed to make sensors, actuators, and device states controllable via a simple HTTP API and your own web interface without the overhead of heavy external frameworks.

**"Open, honest, and transparent."**

WebPi aims to bring the world of C++ and hardware level programming closer to everyone while making the entry point as easy as possible.


---

## ⚛️ The Philosophy
WebPi was born from the experience that developing on the Raspberry Pi is becoming increasingly complex. That classic "GPIO feeling" just quickly making an LED blink has somewhat been lost.

WebPi brings that feeling back. It wraps complex mechanisms into clear, readable, and memorable functions, making C++ accessible to everyone.


---

## ✨ Highlights

* **🌐 Self-contained Ecosystem:**
     - Integrated HTTP server and modular core system. No external web server like Apache or Nginx required.

* **💽 WebPiMemory:**
     - Real RAM? No, but a perfect mirror image. A memory module for every purpose, combined with efficient functions in a lightweight design. With WebPiEasy, hardware control becomes pure high-level programming.
     - Integrated bitmasks for getting started right away.
     - Bit manipulation made easy. Switch bits or store entire sensor values ​​for 8-bit or 16-bit.
     - WebPiMemory is consolidated into a single central 64-bit register. This high-speed design is specifically optimized for resource-efficient operation on embedded systems such as the Raspberry Pi.

* **🛠 Modular Design:**
     - Use only what you need. Header-only classes ready for any use case, whether within WebPi or for standalone projects modular and customizable.
     - The user friendly **WebPiEasy** featuring many simplified wrapper functions similar to an Arduino sketch.
     - From hardware modules (expanders, radio modules, rangefinders) to easy to understand board drivers like SPI, I2C, and UART.

* **🔌 GPIO Control:**
     - Use WebPiGPIOV2, the libgpiod WebPiGPIOD-Wrapper, or other GPIO libs you decide what fits your needs.
     - Configure via `configPin()`, read/write via `setPin()` / `getPin()`. Control GPIOs with short and concise syntax.

* **📖 Your Progress:**
     - Many WebPi functions serve you with default parameters but can be fully customized with your own values.

* **⚠️ WebPi-Apps:**
     - Ready to use apps. Adapt the applications to your needs and turn them into your own project.
     - Everything C++, system headers and WebPi have to offer finds its place here for immediate use or as inspiration for your visions.


---

## 📐 Basic Structure

Have it created using WebPiStart or create it manually. Use the many examples and wpeasy for quick results.

**Start your project**
```

/*******************************
* myproject
*******************************/

#include "webpi.hpp"

WebPi webpi;


void init() {
    // One-time initialization & lib setup
}


void run() {
    // Your loop code (controlled execution)
}


void onclose() {
    // Clean termination of the process called automatically e.g. Ctrl+C:
}


int main() {
    // Hands over lifecycle and signal handling to WebPi
    webpi.main(init, run, onclose);
}

```

**Your project directory structure**
```

myproject/
├── CMakeLists.txt
├── src
│   └── myproject.cpp
└── web
    ├── app.js
    ├── images
    ├── index.html
    └── style.css

```

---

## 🛟 WebPi-Start

A Bash based, menu driven startup tool that manages dependencies and builds at the touch of a button.
 - Create **custom project** structures at the push of a button, using templates for C++, HTML, CSS, JavaScript, and CMakeLists.
 - Build the future ones WebPi Apps and Demo Examples, compare code with the visual web interface see what works, how, and why.
 - **Central control** start/stop, or let the binaries continue running in the background. Have your completed projects set up as a system service.

Control everything from a device of your choice; you only need an SSH connection to your Raspberry Pi.


**Ready to use in a few steps**
```

  cd webpi/webpistart
  
  chmod +x webpistart.sh
  
  ./webpistart.sh
  
```

Great tools e.g.
 - Putty
 - Termius
 - OpenSSH


**⌨️ Main menu**
```

=======================================
              WebPiStart
=======================================



───────────────────────
1) Projects
2) Apps
3) Examples
───────────────────────
t) View backgound tasks
b) View binary status
───────────────────────
p) Prepare system (dependencies)
s) Compare release status
───────────────────────
q) Quit


```


**🆕 Create new project**
```

=======================================
              WebPiStart
=======================================

###    Project configuration    ###


Project name: myproject
  
WebPiServer:
http://192.168.178.8:8989

WebPi libs:
wp_easy.hpp
  
Projects CMakeLists:
add_subdirectory(myproject)
  
Create project directory structure:
projects
├── myproject
│   ├── src
│   │   └── myproject.cpp
│   ├── web
│   │   ├── index.html
│   │   ├── style.css
│   │   └── app.js
│   └── CMakeLists.txt
└── CMakeLists.txt
───────────────────────
1) View CMakeLists.txt
2) View myproject.cpp
3) Create project
c) Cancel

```

---

## 🌐 WebPi & WebPiEasy

It brings back the **WiringPi** experience and the simplicity of programming a microcontroller like an **Arduino**, with the power of C++ programming and the advantages of a modern POSIX operating system.
Consistent, easy-to-remember functions without elaborate names e.g.

**webpi**
- server()
- on()
- send()
- quit()
- **memory**
    - readSlot()
    - writeSlot()
    - clearSlot()
    - readSlotA-D()
    - writeSlotA-D()
  
**gpio**
  - setPin()
  - getPin()
  - configurePin()
  
**uart, spi, i2c**
  - open()
  - close()
  - isOpen()
  
**tcp, udp**
  - write()
  - read()
  - available()
  - connected()

**terminal out**
  - tell()
  - tellb()
  - tellerr()

**hardware inputs & outputs**
 
 **buttons**
  - add()
  - update()
  - remove()

 **buzzer**
  - play()
  - beep()
  - playCustom()
  - playMelody()
  
  
and many more.

---
## 🧱 Framework Architecture Overview
WebPi is modular and clearly structured. The extensions are not hardlinked, meaning they can also be used for your own independent purposes. You simply need to include the available libraries in your project and add them to the CMakeLists—only the ones you actually need.

```

webpi
├── CMakeLists.txt
├── core
│   ├── CMakeLists.txt
│   ├── include
│   │   ├── webpi.hpp
│   │   └── webpi_server.hpp
│   └── src
│       ├── webpi.cpp
│       └── webpi_server.cpp
├── docs
│   └── README.md
├── examples
│   ├── actuators
│   ├── buzzer
│   ├── CMakeLists.txt
│   ├── gethost
│   ├── gpio
│   ├── hellowebpi
│   ├── radioswitch
│   ├── shutter
│   ├── tempsensor
│   └── webpieasy
├── lib
│   ├── CMakeLists.txt
│   ├── extensions
│   │   ├── CMakeLists.txt
│   │   ├── components
│   │   │   ├── CMakeLists.txt
│   │   │   ├── inputs
│   │   │   └── outputs
│   │   ├── devices
│   │   │   ├── CMakeLists.txt
│   │   │   ├── wp_cc1101.hpp
│   │   │   ├── wp_mcp23017_8.hpp
│   │   │   └── wp_vl53l0x.hpp
│   │   ├── driver
│   │   │   ├── CMakeLists.txt
│   │   │   ├── wp_i2c.hpp
│   │   │   ├── wp_spi.hpp
│   │   │   ├── wp_tcp_client.hpp
│   │   │   └── wp_uart.hpp
│   │   ├── gpio
│   │   │   ├── CMakeLists.txt
│   │   │   ├── wp_gpiod_wrap.hpp
│   │   │   └── wp_gpio_v2.hpp
│   │   ├── module
│   │   │   ├── CMakeLists.txt
│   │   │   ├── wp_counter.hpp
│   │   │   ├── wp_filetools.hpp
│   │   │   ├── wp_logbook.hpp
│   │   │   ├── wp_minimodbus.hpp
│   │   │   └── wp_mqtt.hpp
│   │   └── README.md
│   └── wpeasy
│       ├── CMakeLists.txt
│       ├── README_DE.md
│       ├── README.md
│       ├── wp_easy.hpp
│       ├── wp_json.hpp
│       ├── wp_math.hpp
│       ├── wp_out.hpp
│       ├── wp_parse.hpp
│       ├── wp_string.hpp
│       ├── wp_system.hpp
│       └── wp_time.hpp
├── projects
│   └── README.md
├── resources
│   ├── benchmark
│   ├── images
│   ├── tools
│   ├── webpistart
│   ├── webpicode
│   └── README
├── source.list
├── templates
│   ├── cmake
│   ├── libs
│   ├── README.md
│   ├── web
│   └── webpi
└── webpistart
     ├── bash
     │   ├── apps.bash
     │   ├── build.bash
     │   ├── conf.bash
     │   ├── dependencies.bash
     │   ├── examples.bash
     │   ├── main.bash
     │   ├── msg.bash
     │   ├── projects.bash
     │   ├── sources.bash
     │   └── status.bash
     ├── CHANGELOG.md
     ├── data
     │   └── remote_source.list
     ├── README.md
     ├── templates
     │   ├── base.cpp
     │   ├── cmakelists.txt
     │   └── web
     │       ├── app.js
     │       ├── images
     │       ├── index.html
     │       └── style.css
     └── webpistart.sh


```

---

🔢 The Bitmask Concept
WebPi makes binary logic visible. Demo Examples like `actuators` demonstrate directly how the internal 8-bit mask interacts with the webinterface.

<div align="center">
<img src="resources/examples/actuators.jpg" alt="WebPi Actuators" width="40%" height="40%"/>

Clarity through visualization Bitmask states in real-time.
</div>


---

📈 Ready for Data
Whether it's temperature logs or system monitoring, WebPi helps you realize your ideas.
<div align="center">
<img src="resources/examples/tempsensor.jpg" alt="WebPi Temperature Graphs" width="40%" height="40%"/>
  
Example of sensor integration with SVG charts and logging functionality.
</div>


---

🛠️ WebPi Status
WebPi is in an advanced stage, nearing release.
You can follow the development via the source list and the regular news.

Stay tuned!


---

📖 Legal disclaimer and licenses

Logo & Branding:

The WebPi logo is an independent design and not an official graphic of the Raspberry Pi Foundation.


Legal Disclaimer:

Raspberry Pi is a trademark of the Raspberry Pi Foundation. This project is not affiliated with, endorsed by, or associated with the Raspberry Pi Foundation.


License:

This project is under the [MIT License](LICENSE).
