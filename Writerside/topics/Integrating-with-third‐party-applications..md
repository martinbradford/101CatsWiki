# Integrating with third-party applications

**101Cats** provides good support for integration with third-party applications including log books and digital mode applications such as WSJT-X. As well as controlling the radio itself, 101Cats also functions as a hub to allow multiple third-party applications to connect to the radio. It implements multiple virtual FTdx101s so that each third-party application thinks it has sole control of the radio and 101Cats takes care of routing commands and responses accordingly so that no two applications will block each other.

101Cats makes use of an external virtual serial port driver application in order to establish the interfaces with the third-party applications. There are several virtual serial port driver applications available including [com0com](https://sourceforge.net/projects/com0com/), [Eltima Virtual Serial Port Driver](https://www.eltima.com/products/vspdxp/) and [Eterlogic VIRTUAL SERIAL PORTS EMULATOR](https://eterlogic.com/Products.VSPE.html). Com0com is probably the most widely used - it is free and works well. The others may have more modern user interfaces, but they cost money and don't seem to have any significant benefit over com0com. Note that Windows 11 is more touchy that previous versions about third-party drivers. Com0com is available both signed and unsigned - you probably want to install the unsigned version with Windows 11. 

Once you have chosen and installed your virtual serial port framework, you will have to create virtual serial port pairs to support the third-party applications that you wish to connect. Think of each virtual serial port pair as a virtual cable that can connect two applications together. You will need as many virtual serial port pairs as you have third-party applications to connect (actually, this may not be strictly true if you use Omnirig - see below).

I use Com0com and the screenshot below shows my configuration:

![image](https://github.com/martinbradford/101Cats/assets/30900693/2d672cc7-1f7a-4f16-a7a5-1bbb089464a7)

If you are creating multiple port-pairs, it can become difficult to keep track of them. Adopt a numbering scheme which makes it easy to remember the two ends of a port pair - in my example, the port numbers at each end differ by 20. If you are using com0com, you probably don't need to change any of the port parameters from their default settings.

Once you have created the port pairs, you need to configure one end of each of them into 101Cats. You can do this through the configuration dialogue box of 101Cats as shown below. Note that the configuration dialogue box does not currently include functionality to add or remove ports from the configuration. The standard configuration file includes six port entries and you can update these to suit your requirements. If you don't need all six, mark some of them as not enabled. If you need more than six, you'll have to manually edit the **config.xml** file.


![image](https://github.com/martinbradford/101Cats/assets/30900693/86c74720-afb8-4554-bc91-f6acd2bd68b0)


Note that each virtual port configured into 101Cats is one end of a virtual serial port pair - the other end will be used by the corresponding application. In my example, port COM48 is configured for WSJT-X. Under my chosen numbering scheme, COM48 is one end of a pair with COM28 - hence the configuration of WSJT-X on my PC is:

![image](https://github.com/martinbradford/101Cats/assets/30900693/1cf67aa1-7972-40fc-adf7-8e2c251267be)

You'll need to determine the **Auto Information** setting by trial and error in most cases. Auto Information is a function of the FTdx101 which can be turned on and off by the application - when it is on, the radio sends a continuous stream of status messages to the application, avoiding the need for the application to poll repeatedly for data. 101Cats is able to replicate the Auto Information stream out to each third-party application but doing so unnecessarily will increase the load on your PC, so try disabling it and checking if the application still works. Auto Information is controllable on a per application basis.

## Omnirig

To Be Completed