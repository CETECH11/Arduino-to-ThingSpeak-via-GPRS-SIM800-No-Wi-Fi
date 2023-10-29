# Arduino-to-ThingSpeak-via-GPRS-SIM800-No-Wi-Fi

![alt text](https://hackster.imgix.net/uploads/attachments/1638668/_dsc0470_Gy8aaEtZi9.JPG?auto=compress%2Cformat&w=740&h=555&fit=max)

Sending data from an Arduino microcontroller to the ThingSpeak platform using a GPRS module is not a novel project concept. While it may appear outdated in numerous regions, owing to the rapid evolution of communication technologies such as 2G, 3G, 4G, 5G, and the potential for 6G, this is not the case in my country. In India, 2G technologies remain prevalent, and major network operators have confirmed their intent to sustain 2G services.

The legacy project documents that were originally designed with the SIM800 module may necessitate slight adjustments. This project will prove invaluable to those who continue to rely on 2G and GPRS technology. It offers essential support and guidance for individuals who intend to persist with these communication methods.
Sending data from an Arduino microcontroller to the ThingSpeak platform using a GPRS module, specifically the SIM800, is a fundamental concept. The crucial aspect is that this communication method operates independently of Wi-Fi, constituting an IoT connectivity solution that relies on GPRS for data transmission.

![alt text](https://hackster.imgix.net/uploads/attachments/1638678/image_KSsdoq1XZc.png?auto=compress%2Cformat&w=740&h=555&fit=max)

In this project, LM35 temperature sensor data is being transmitted to the ThingSpeak platform through an Arduino Nano and a SIM800 module. The SIM800 module is leveraged to establish a GPRS connection, facilitating the transmission of data to ThingSpeak at specified intervals.

To ensure a reliable connection between ThingSpeak and the hardware, users must configure the SIM800 module to establish a connection with their mobile network. This configuration encompasses setting the Access Point Name (APN) specific to their mobile carrier. It's important to note that the specific AT commands for this configuration may vary based on the user's chosen mobile network provider.

For this project, I utilized the services of the network provider Airtel to establish the connection.

Communication between the hardware components, specifically the SIM800 module, Arduino Nano, and ThingSpeak platform, relies entirely on AT commands. To ensure successful project implementation and effectively troubleshoot any issues that may arise, users must possess a basic understanding of SIM800 AT commands. This knowledge is crucial for configuring, managing, and diagnosing the communication process and resolving potential challenges during the project.

![alt text](https://hackster.imgix.net/uploads/attachments/1638696/bd_ZrstR9akG2.jpg?auto=compress%2Cformat&w=1280&h=960&fit=max)

The SIM800 serial module's TCP/IP application offers two connection modes, selectable through the AT command `AT CIPMUX=<n>`.

When `AT CIPMUX` is set to 0 (`AT+CIPMUX=0`), it operates in single-link mode.
When `AT CIPMUX` is set to 1 (`AT+CIPMUX=1`), it operates in multi-link mode.
By default, the module is configured in single-link mode.

In single-link mode, the SIM800 serial module can function in both transparent and non-transparent transmission modes. In both of these modes, the module can be configured as either a TCP/UDP client or a TCP server.

In multi-link mode, the SIM800 serial module operates solely in non-transparent mode. In this mode, it can serve as a TCP/UDP client, allowing for the establishment of a maximum of 6 connections. It can also be configured as a TCP server, with support for 5 TCP/UDP clients. SIM800C TCP/IP operates with a multi-client architecture by default, enabling up to five sockets for TCP or UDP connections.

In the upcoming demonstrations, our focus will be on the client communication capabilities of the SIM800C module. Specifically, we will explore its operation in single-link non-transparent mode and transparent mode.

Client communication in non-transparent mode

Client communication in non-transparent mode refers to the way the SIM800C module interacts with remote servers or devices when it acts as a client, transmitting data using a specific protocol such as TCP or UDP. In non-transparent mode, the module sends and receives data through AT commands and does not directly pass data between the microcontroller and the remote server.

This mode provides control over the data transmission process, allowing you to send and receive data, manage connections, and configure communication settings using AT commands. It is suitable for applications where you need fine-grained control over the communication process and want to ensure data integrity.

To use the SIM800C in client communication in non-transparent mode, you will typically configure the module using appropriate AT commands and establish connections with remote servers or devices for data exchange.

Client communication in transparent transmission mode

Client communication in transparent transmission mode refers to the SIM800C module's ability to act as a client while allowing data to flow directly between the microcontroller (e.g., an Arduino) and a remote server or device. In this mode, the SIM800C module operates as a transparent bridge, forwarding data between the microcontroller and the remote server without the need for explicit AT commands to send or receive each piece of data.

This mode simplifies data transfer by treating the SIM800C module as a transparent conduit. Data sent by the microcontroller is transmitted to the remote server without manual packetization, and data received from the server is forwarded to the microcontroller without manual processing.

Using the SIM800C in transparent transmission mode is advantageous when you want to streamline data transfer and reduce the complexity of managing data packets and AT commands for each communication task. It's particularly useful for applications where data throughput and efficiency are essential.

![alt text](https://hackster.imgix.net/uploads/attachments/1642551/3_t46n7cozgf.PNG?auto=compress%2Cformat&w=740&h=555&fit=max)

You must check out [PCBWAY](https://www.pcbway.com/) for ordering PCBs online for cheap!

You get 10 good-quality PCBs manufactured and shipped to your doorstep for cheap. You will also get a discount on shipping on your first order. Upload your Gerber files onto PCBWAY to get them manufactured with good quality and quick turnaround time. [PCBWay](https://www.pcbway.com/) now could provide a complete product solution, from design to enclosure production. Check out their online Gerber viewer function. With reward points, you can get free stuff from their gift shop.Also, check out this useful blog on PCBWay Plugin for KiCad from [here](https://www.pcbway.com/blog/News/PCBWay_Plug_In_for_KiCad_3ea6219c.html). Using this plugin, you can directly order PCBs in just one click after completing your design in KiCad.
