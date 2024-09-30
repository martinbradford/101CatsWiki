# Additional Hardware

101Cats is designed to work with several different external devices that can enhance its operation. These are briefly described here. More detailed documentation will be added in the future - if you are in a hurry to try any of these, post a message on the Discussions board requesting additional information.

## An external SDR

The FTdx101 has good support for an external SDR connected to one of the RF outputs on the rear panel. 101Cats builds on this by offering functionality to interface to a third-party SDR application running on the same PC so that they cooperate. The author uses an SDRPlay RSP1A receiver with the SDR Console application. 101Cats has also interfaced successfully to the SDRUno application offered by SDRPlay although this has not been tested recently. If you try this and find that it does not work, raise it as an issue and it will be fixed. 

The configuration of 101Cats and SDR Console is too complex to describe here - a separate page will be added to the Wiki shortly. Once it is configured at both ends, the **To SDR** and **From SDR** buttons to the right of the main window become active and will support the synchronization of frequency in either direction. If you enable **Tracking** in SDR Console, then the two applications remain synchronized automatically and you can tune the FTdx101 by clicking in the SDR Console spectrum display.

## An external video digitizer.

The FTdx101 has a video output on the back panel which will drive an external monitor to give you a larger display. It works well enough, but represents a significant investment and occupies quite a lot of space in the shack. You can buy a cheap USB video digitizer through Amazon (and other web retail sources) for around $20 which will allow 101Cats to capture the video output from the radio and display it in a movable and realizable window on your PC screen. 
![image](https://github.com/martinbradford/101Cats/assets/30900693/5d969778-f67d-49d1-b459-bf219bd7e5b9)


101Cats will allow you to tune the radio by pointing into the waterfall display in this window and clicking with your mouse. An example of the display is shown below ::

![two](https://github.com/martinbradford/101Cats/assets/30900693/f8467b75-4b51-46b2-a9ae-1889939d7220)

## A Contour Shuttle tuning wheel

Contour Design manufacture [multi-media controllers](https://contour-design.co.uk/collections/multimedia-controller) which 101Cats supports as dedicated tuning knobs. 

![image](https://github.com/martinbradford/101Cats/assets/30900693/4d087657-67dd-4af4-a41f-1f31142a6e6b)

The Contour Multimedia Controller Xpress has five buttons, a "jog dial" and a digitizer wheel. 101Cats uses these to tune and control the radio in a natural manner comparable with the front panel controls. The Multimedia Controller PRO v2 has additional buttons that could be programmed to perform other tasks - though this would require additional code in 101Cats.


