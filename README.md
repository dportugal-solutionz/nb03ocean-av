# **PIMCO NB 03-Ocean Multipurpose Room: AV Files**

"Room Controls", [User Interface Extension Files](https://github.com/brianlopezpimco/nb03ocean-av#user-interface-extension-files) have all the graphics for the Room Controls panel on the conference room touch panel. A table of widget IDs and panel graphics can be found in the [User Interface Extensions Widget IDs](https://github.com/brianlopezpimco/nb03ocean-av#user-interface-extension-widget-ids) section.

Crestron [Control System Files](https://github.com/brianlopezpimco/nb03ocean-av#control-system-files) contain the logic needed to for "Room Controls" (lights & shades). To replace or upload new control system code to the processor; follow the [Control System Files Installation](https://github.com/brianlopezpimco/nb03ocean-av#control-system-files-installation) section below. The same program will work for all PIMCO standard conference rooms.

[Wiring Schematics](https://github.com/brianlopezpimco/nb03ocean-av#wiring-schematics) detail how each of the physical system components are connected together; each of the wiring schematic pdfs can be downloaded in the [Wiring Schematics](https://github.com/brianlopezpimco/nb03ocean-av#wiring-schematics) section below.

## **TABLE OF CONTENTS:**

- [User Interface Extension Widget IDs](https://github.com/brianlopezpimco/nb03ocean-av#user-interface-extension-widget-ids)
- [User Interface Extension Installation](https://github.com/brianlopezpimco/nb03ocean-av#user-interface-extension-installation)
- [Control System Files](https://github.com/brianlopezpimco/nb03ocean-av#control-system-files)
- [Control System Files Installation](https://github.com/brianlopezpimco/nb03ocean-av#control-system-files-installation)
- [Wiring Schematics](https://github.com/brianlopezpimco/nb03ocean-av#wiring-schematics)
- [Contributions](https://github.com/brianlopezpimco/nb03ocean-av#contributions)
- [Additional Resources](https://github.com/brianlopezpimco/nb03ocean-av#additional-resources)

## **USER INTERFACE EXTENSION WIDGET IDS:**

### **pimco-roomcontrols-singledisplay-pnl:**

![Single Display](/images/roomcontrols-singledisplay-pnl.PNG)

| USER INTERFACE LABEL     | WIDGET ID         |
| ------------------------ | ----------------- |
| Main Display: On Button  | display01-on-btn  |
| Main Display: Off Button | display01-off-btn |

### **pimco-roomcontrols-singledisplay-lights1x2-pnl:**

![Single Display with Lighting1x2](/images/roomcontrols-singledisplay-lights1x2-pnl.PNG)

| USER INTERFACE LABEL          | WIDGET ID             |
| ----------------------------- | --------------------- |
| Overhead Lights: On Button    | lightzone01-on-btn    |
| Overhead Lights: Off Button   | lightzone01-off-btn   |
| Overhead Lights: Up Button    | lightzone01-up-btn    |
| Overhead Lights: Down Button  | lightzone01-down-btn  |
| Solar Shades: Open Button     | shadezone01-open-btn  |
| Solar Shades: Close Button    | shadezone01-close-btn |
| Solar Shades: Up Button       | shadezone01-up-btn    |
| Solar Shades: Down Button     | shadezone01-down-btn  |
| Blackout Shades: Open Button  | shadezone02-on-btn    |
| Blackout Shades: Close Button | shadezone02-off-btn   |
| Blackout Shades: Up Button    | shadezone02-op-btn    |
| Blackout Shades: Down Button  | shadezone02-down-btn  |

### **pimco-roomcontrols-singledisplay-lights1x3-pnl:**

![Single Display with Lighting1x3](/images/roomcontrols-singledisplay-lights1x3-pnl.PNG)

| USER INTERFACE LABEL          | WIDGET ID             |
| ----------------------------- | --------------------- |
| Overhead Lights: On Button    | lightzone01-on-btn    |
| Overhead Lights: Off Button   | lightzone01-off-btn   |
| Overhead Lights: Up Button    | lightzone01-up-btn    |
| Overhead Lights: Down Button  | lightzone01-down-btn  |
| Solar Shades: Open Button     | shadezone01-open-btn  |
| Solar Shades: Close Button    | shadezone01-close-btn |
| Solar Shades: Up Button       | shadezone01-up-btn    |
| Solar Shades: Down Button     | shadezone01-down-btn  |
| Blackout Shades: Open Button  | shadezone02-open-btn  |
| Blackout Shades: Close Button | shadezone02-close-btn |
| Blackout Shades: Up Button    | shadezone02-up-btn    |
| Blackout Shades: Down Button  | shadezone02-down-btn  |
| Drapery Track: Open Button    | shadezone03-open-btn  |
| Drapery Track: Close Button   | shadezone03-close-btn |
| Drapery Track: Up Button      | shadezone03-up-btn    |
| Drapery Track: Down Button    | shadezone03-down-btn  |

![Dual Display](/images/roomcontrols-dualdisplay-pnl.PNG)

| USER INTERFACE LABEL      | WIDGET ID         |
| ------------------------- | ----------------- |
| Left Display: On Button   | display01-on-btn  |
| Left Display: Off Button  | display01-off-btn |
| Right Display: On Button  | display02-on-btn  |
| Right Display: Off Button | display02-off-btn |

## **USER INTERFACE EXTENSION INSTALLATION:**

To upload a user interface extension file; first login to the codec...

![<Login Screen>](/images/endpoint-login-screen.PNG)

Browse to "User Interface Extensions" from the main menu...

![<User Interface Extensions>](/images/ui-extension-zoomtools.PNG)

Select hamburger menu at top right, and select "Merge from File". NOTE: If you select "Import from File" any existing UI extensions will be overwitten when the new extension is loaded...

![<User Interface Extensions>](/images/ui-extension-merge-file.PNG)

Confirm your UI is loaded correctly, and select "Uploade to Device" from the top right menu to push the UI elements to the endpoint...

![<User Interface Extensions>](/images/ui-extension-loaded.PNG)

## **CONTROL SYSTEM FILES:**

Most of the UI/UX is controlled internally by the codec and the WebEx navigator. For rooms with "Room Controls" (lights & shades), a Crestron control system processor is installed and connected to the codec. The control system registers for feedback from the codec and will send the appropriate commands to the lighting system. The following Crestron Control System program will work for systems with any combination of the endpoint configurations and UI extensions above.

| CONFERENCE ROOM APPLICATION(S)                           | CRESTRON CONTROLS SYSTEM FILE(S) |
| -------------------------------------------------------- | -------------------------------- |
| All PIMCO Standard Conference Rooms with "Room Controls" | pimco-room-controls-cp4 v1.1.ipz |

SIMPL Windows Program: Crestron program registers the CP4 with the endpoint for feedback, and maintains "heartbeat" (pimco-roomcontrols-cisco). Widgets from the lighting panel are handled and lighting commands are executed by the lighting module (pimco-roomcontrols-lutron). Widgets from the displays panel are handled and executed by the dispays module (pimco-roomcontrols-samsung). 

![Simpl Windows Code](/images/simpl-code.png)

**SIMPL+ Codec Module:** Registers codec for feedback and maintains heartbeat...

![SIMPL Plus Code](/images/simpl-plus-cisco-code.png)

**SIMPL+ Lighting Module:** Handles lighting widgets and executes Lutron lighting controller commands...

![SIMPL Plus Code](/images/simpl-plus-lutron-code.png)

**SIMPL+ Displays Module:** Handles display widgets and executes Samsung display commands...

![SIMPL Plus Code](/images/simpl-plus-samsung-code.png)

## **CONTROL SYSTEM FILES INSTALLATION:**

In order to load compiled code to a Crestron processor, you must install Crestron Toolbox. You may need to register with Crestron and request access the software. Once installed, open Toolbox, then open the "Easy Config" tool. (tools menu). Once open, click the pencil at bottom, enter address of processor to connect...

![<Connecting to Toolbox>](/images/toolbox-connect.png)

Once connected. select the "Program" button. Browse your computer for the file and select send to load the file...

![<Uploading Code>](/images/toolbox-send-code.png)

## **WIRING SCHEMATICS:**

| CONFERENCE ROOM APPLICATION                 | WIRING SCHEMATIC FILE                                  |
| ------------------------------------------- | ------------------------------------------------------ |
| Standard Conference Rooms (combined PDF)    | pimco-standard-conference-rooms-schematics.pdf         |
| Single Display Conference Rooms without DSP | pimco-singledisplay-conference-rooms-schematic.pdf     |
| Dual Display Conference Rooms without DSP   | pimco-dualdisplay-conference-rooms-schematic.pdf       |
| Single Display Conference Rooms with DSP    | pimco-singledisplay-conference-rooms-dsp-schematic.pdf |
| Dual Display Conference Rooms with DSP      | pimco-duladisplay-conference-rooms-dsp-schematic.pdf   |

## **CONTRIBUTIONS:**

All endpoint configurations, user interface extensions, and JavaScript macros were created by [Brian Lopez](https://www.linkedin.com/in/engineerblopez/) for [PIMCO](https://www.pimco.com/en-us/) TeleMedia in 2022.

## **ADDITIONAL RESOURCES:**

- [Cisco Room Controls Design Guide](https://www.cisco.com/c/dam/en/us/td/docs/telepresence/endpoint/ce915/sx-mx-dx-room-kit-boards-customization-guide-ce915.pdf)
- [Cisco Room Kit Plus Command References (ce 9.15)](https://www.cisco.com/c/dam/en/us/td/docs/telepresence/endpoint/ce915/collaboration-endpoint-software-api-reference-guide-ce915.pdf)
- [Cisco RoomOS API References](https://roomos.cisco.com/xapi)

