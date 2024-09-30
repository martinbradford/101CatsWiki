# User Interface

101Cats is a Windows program and follows the Windows User Interface conventions fairly closely. The majority of controls are combo-boxes, sliders and toggle switches and operate as you would expect. The intention is that it should be largely mouse driven and sliders should react to mouse clicks, mouse drags and the rotation of the mouse wheel. Surprisingly, none of these interactions come without some programming effort and it is almost certainly the case that I have not implemented the mouse wheel on some of the less frequently used sliders - if you find one, ping me a message and I'll fix it in a future release. Where a slider has a sensible default value, it should respond to a double click by resetting to that value. Try setting the filter shift to some non-zero value, then double clicking it - it will reset back to zero. I have not implemented that on every slider - if you think that it should be present elsewhere, tell me and I'll add it in the future.

The two meter controls are hand-carved code - I could not find any off-the-shelf meter control that I could use at a reasonable price. They were complex to implement and are still not perfect. The scales were determined by inspection and may not accurately reflect the values displayed on the radio front panel - if you find any glaring errors, let me know.

The frequency displays are also hand-carved code. They respond to the mouse wheel which is the primary method of tuning. One digit is highlighted at all times and this is the digit that is varied by the mouse wheel. Clicking on a different digit will select it such that you can choose the tuning rate. You can also use the keyboard to temporarily adjust the tuning rate - hold down the "ctrl" key while you turn the mouse wheel to multiple the tuning rate by ten, the "shift" key multiplies it by 100 and "ctrl" + "shift" multiplies it by 1000. Double clicking in the frequency display rounds it off to the nearest kHz.

You can also enter frequencies by typing them on the keyboard. If 101Cats is the application with focus, typing any digit on the keyboard will open up a data entry window where you can key in an exact frequency. Hitting "enter" will tune to the new frequency.

## Other Functions

The column of buttons down the right hand side of the window should be reasonably self-explanatory, but here are a few notes... "TW" opens the "Trace Window" which displays the data stream to and from the radio. It also allows you to enter CAT commands and send them to the radio. This is intended for me to debug the code - use it with care unless you are sure of what you are doing. It should not be possible to damage the radio through this window, but you certainly could get it into some strange state which is difficult to undo without a reset.

"External Tune" saves the current power level and mode settings, then switches to AM, reduces the power to 10W and puts the radio into transmit. When you release the button, the radio is put back to receive and the previous power and mode are reinstated. In order to avoid tuning up on a frequency that is in use, right clicking this button will QSY up 3kHz before putting out the carrier and QSY back down on release. Obviously, this could result in you shifting to another busy frequency, but the FTdx101 has a good bandscope and it only takes a glance at the screen to know if it is safe to QSY up.

The "Mute" button turns off both receivers. This is a toggle button - clicking it again will restore the receivers to their previous state.

The "To SDR" and "From SDR" buttons transfer the current frequency between 101Cats and an external SDR program such as SDR Uno or SDR Console. I know that both of those programs implement a function to synchronise their tuning with that of an external radio, but this function is limited and did not match my style of operation. There is a more detailed explanation of this on another page of this Wiki.

The "<=>" button swaps frequency and mode between Main and Sub.

The "Internal Tuner" and "Tune" buttons do what they say - turn the internal tuner on/off and initiate a tuning cycle.

The "Zero In" and "CW Spot" buttons also do what they say - only functional with the radio in CW mode.

The "Spectrum" button opens up a second window that displays the radio's spectrum display and allows you to control it. The FTdx101 does not output spectrum data over the USB interface, so this window is only functional if you have the DVI output on the back panel connected to the PC via a video digitizer. This is too complex to describe here and will be the subject of another Wiki page.

The "Keyer Memory" button brings up a dialogue box that roughly matches the functionality of a Yaesu FH-2 keypad. This window needs work - it is functional, but not polished.

The "History" button brings up the "Tuning History" window. This is another "work in progress", but already very useful. You can set a timeout (which defaults to 10 seconds) and, if the radio remains tuned to a frequency for more than this period of time, an entry will be made in the history window. Double clicking an entry in the history list will tune back to that frequency and mode. You can annotate an entry in the history list to remind yourself of what you heard there and you can clear the entire list or individual entries. Gone are the days when you were tuning around, heard an interesting DX station, made a mental note to go back and try to work it, then completely forgot the frequency he was on. It also helps to avoid "finger trouble" as you accidently jog the tuning knob and lose the station you were talking to!

The "DX Cluster" button brings up a window that displays the output of a DX Cluster server. This is very definitely a work-in-progress - it does work, but it has a lot of rough edges. It will be improved significantly in a future release.

Below the buttons, you'll see "APO Time" and "APO Enabled" - these are Automatic Power Off. The box below "APO Enabled" is the count-down - if it gets to zero, the radio is powered off. Any activity in the window will reset the APO Timer.

"SWR Check" turns on a High SWR warning function. If the radio reports a high SWR reading to 101Cats, then it will be forced out of transmit and a warning message box displayed. Note that, during antenna tuning the SWR may go high at times. 101Cats implements a delayon the High SWR warning function - this defaults to 1 second and can be configured via the configuration file.

Below the SWR Check box, there are several static text fields. The top one is the version number of 101Cats. Below that, there are three numeric fields - these are the lengths of various internal data queues and are there to assist with debugging the code. They should idle at zero and never go above four or five. The only exception to this is at startup when there is a lot of interaction between the application and the radio and you may see queue lengths increase significantly.

## Speech Processor Controls

The speech processor on the FTdx101 series is more complex than that on many other radios and getting the setting wrong can make the transmission sound bad and, possibly, excessively wide. There are three sliders - "Mic Gain", "Speech Processor" and "AMC" towards the bottom of the 101Cats window that control the speech processor parameters. There is also a toggle switch, "Lock Processor" which disables these controls. Getting the processor set                    to match your microphone and operating style can require a significant amount of effort and I wanted to guard against accidentally "jogging" a setting and undoing all my careful work!
