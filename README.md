# DBF X1 Glider – AIAA Design Build Fly Competition Entry

## ✈️ Overview
This was a project I contributed to for my DBF (Design, Build, Fly) club. Essentially, DBF is a club where we design, build, and fly our own self-made plane to compete in an AIAA competition. This project was built for the 2025 AIAA Design/Build/Fly competition, which tasked university teams with designing and fabricating an RC aircraft capable of deploying an autonomous glider ("X-1 test vehicle") mid-flight. The aircraft had to complete multiple missions involving payload transport, mid-air deployment, and ground assembly, all under strict design, weight, and flight constraints. <br />
My job for this competition was to work with our aerodynamics team lead to assemble and configure our flight controller to navigate its way to a certain waypoint, and to design a circuit to communicate to the flight controller that it had been released from the main RC plane.

## 👨‍💻 Personal Contributions
- **Flight Controller** – I was one of three main team members who worked with the flight controller (A SpeedBee Wing f405 flight controller). Our initial job was to find a way for the flight controller to read an external voltage. This is how we planned on communicating to the flight controller that the X1 had been released. I first started by reading the documentation for the flight controller. I looked over what pins did what, how they could be used, and any voltage or current limits they had. After a bit of research, I found that feeding an external voltage to the RSSI pin may work for what we intended, but we weren't sure how to tell the flight controller what to do when the external voltage was applied. In my search for a solution to this, I had to learn how the flight controller works, how it is put together, and how it can be integrated with software systems such as ArduPilot, Betaflight, and INAV. INAV was our initial software of choice to help configure the flight controller, and after a lot of testing with Arduino and breadboard circuits, we were able to get our flight controller accurately reading an external voltage. We then used INAV to make the flight controller turn on a strip of LED lights when the external voltage was applied, which was a proof of concept for what we later intended to use INAV to configure. We then later had to switch to ArduPilot due to some minor issues we were having with INAV.
- **Circuit Design** - I was tasked with designing a circuit that could provide an external voltage to our flight controller, but only once the X1 had been released. For this, I decided that a limit switch circuit was our best option. From there, I checked the flight controller's documentation page to see what the voltage and current limitations were for the pin we decided to work with (RSSI Input), and designed a circuit on paper for a circuit that provided an external voltage that stayed within the allowable ranges. I then took that circuit and designed it in Everycircuit, which is a circuit simulation website. After seeing that my paper calculations and circuit design were correct, I used a SBB (Solderless Breadboard) and Arduino to test my designed circuit on the flight controller itself, and it worked as intended. I then turned to CAD to design a fixture that could hold the limit switch in place on the X1. After doing so, we just needed to configure the actual circuit on the glider.

## 🛠 Tools & Technologies
- **Onshape** - This was the CAD software our team chose to use for this project.
- **Everycircuit** - Circuit design simulation website.
- **Soldering tools** - Used for integrating the physical circuit on the plane.
- **INAV** - Flight controller configurator software, which we initially used for our flight controller.
- **SpeedyBee Flight controller** - The flight controller our team chose to use for our glider.
- **Arduino** - Used for testing circuit integration with the flight controller.

## 🔗 Useful Links
- Flight Controller Documentation: https://store-fhxxhuiq8q.mybigcommerce.com/product_images/img_SpeedyBee_F405_WING_APP/SpeedyBee_F405_WING_APP_Manual_V1.1-EN.pdf
- AIAA 2024-2025 Competition Rules: https://aiaa.org/wp-content/uploads/2024/12/dbf-rules-2025.pdf
- DBF Website: https://www.coloradodbf.com/
- INAV Documentation: https://github.com/iNavFlight/inav
