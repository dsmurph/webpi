<div align="center">
  <img src="resources/webpi.png" alt="WebPi Logo" width="100">
</div>
<h3 align="center">WebPi – The Hardware and Software Logic Framework</h3>
<br>
<div><h6><a href="README.md">German version</a> | <a href="STORY.md">Story of WebPi</a></h6></div>

---

**🚀 WebPi: The bridge between modern Linux and your hardware projects.**

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

* **🔢 Bitmask Logic:**
     - Builtin bitmasks to get you started instantly.
     - Bit manipulation designed for understanding. Toggle bits or store entire sensor values for 8bit or 16bit states.

* **🛠 Modular Design:**
     - Use only what you need. Header-only classes ready for any use case, whether within WebPi or for standalone projects modular and customizable.
     - The user friendly **WebPiEasy** featuring many simplified wrapper functions similar to an Arduino sketch.
     - From hardware modules (expanders, radio modules, rangefinders) to easy to understand board drivers like SPI, I2C, and UART.

* **🔌 GPIO Control:**
     - Use WebPiGPIO V2, the libgpiod + wrapper, or other GPIO libs you decide what fits your needs.
     - Configure via `configPin()`, read/write via `setPin()` / `getPin()`. Control GPIOs with short and concise syntax.

* **📖 Your Progress:**
     - Many WebPi functions serve you with default parameters but can be fully customized with your own values.

* **🛟 WebPi-Start:**
     - A Bash based, menu driven startup tool that manages dependencies and builds at the touch of a button.
     - For an easy start it builds the **WebPiUI** control and learning platform allowing you to dive right in.
     - Build examples and compare code with the visual web interface see what works, how, and why.

* **⚠️ WebPi-Apps:**
     - Ready to use apps. Adapt the applications to your needs and turn them into your own project.
     - Everything C++, system headers and WebPi have to offer finds its place here for immediate use or as inspiration for your visions.


---

## 🧱 Architecture Overview
WebPi is modular and clearly structured. The extensions are not hardlinked, meaning they can also be used for your own independent purposes.

```text

WebPi/
├─ core/            # Basic syntax structure (Arduino/Pico style), User API, internal bitmasks, webserver
├─ apps/            # Central directory for WebPi applications to use, extend, and customize. 
├─ docs/            # First step advanced function descriptions and project information.
├─ extensions/      # Extensions to make your life easier.
│  ├─ webpidevices/    # Popular hardware modules supported and expanded over time.
│  ├─ webpimodules/    # Board tools with simple and intuitive interfaces.
│  ├─ webpidrivers/    # Base drivers for GPIO controllers and pin management. 
│  └─ webpieasy/       # A collection of wrappers for an easy start. Simple functions, memorable names, without hiding the C++ core.
├─ examples/        # From "Hello WebPi" to SVG temperature graphs and handson bitmask usage. 
└─ webpiStart       # Your first step. Checks resolves dependencies, builds WebPiUI, examples and start the binarys.

```


---

🔢 The Bitmask Concept
WebPi makes binary logic visible. Examples like `actuators` or `shutter` demonstrate directly how the internal 8-bit mask interacts with the webinterface.

<div align="center">
<img src="resources/actuators.jpg" alt="WebPi Actuators" width="40%" height="40%"/>

Clarity through visualization Bitmask states in real-time.
</div>


---

📈 Ready for Data
Whether it's temperature logs or system monitoring, WebPi helps you realize your ideas.
<div align="center">
<img src="resources/tempsensor.jpg" alt="WebPi Temperature Graphs" width="40%" height="40%"/>
Example of sensor integration with SVG charts and logging functionality.
</div>


---

🛠️ WebPi Status
WebPi is in an advanced stage, nearing release.
You can follow the development via the source list.
Stay tuned!
