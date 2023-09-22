# **PIMCO NB 03-Ocean MPR: AV Systems Files**

Biamp [DSP System Files](https://github.com/brianlopezpimco/nb03ocean-av#dsp-system-files-files) contain the audio dsp program that controls how the AV system's audio is proccessed. To replace or upload a new DSP program to a processor, follow the [DSP System Files Installation](https://github.com/brianlopezpimco/nb03ocean-av#dsp-system-files-installation) section below.

Cisco [User Interface Extension Files](https://github.com/brianlopezpimco/nb03ocean-av#user-interface-extension-files) contain all the graphics for the room controls panel. To replace or upload new user interface extensions to a codec, follow the [User Interface Extension Files Installation](https://github.com/brianlopezpimco/nb03ocean-av#user-interface-extension-files-installation) section below.

Crestron [Control System Files](https://github.com/brianlopezpimco/nb03ocean-av#control-system-files) contain the control system program that controls the behavior of the AV system and it's periferal components. To replace or upload new control system code to a processor, follow the [Control System Files Installation](https://github.com/brianlopezpimco/nb03ocean-av#control-system-files-installation) section below.

## **TABLE OF CONTENTS:**

- [DSP System Files](https://github.com/brianlopezpimco/nb03ocean-av#dsp-system-files-files)
- [DSP System Files Installation](https://github.com/brianlopezpimco/nb03ocean-av#dsp-system-files-installation)
- [User Interface Extension Files](https://github.com/brianlopezpimco/nb03ocean-av#user-interface-extension-files)
- [User Interface Extension Files Installation](https://github.com/brianlopezpimco/nb03ocean-av#user-interface-extension-files-installation)
- [Control System Files](https://github.com/brianlopezpimco/nb03ocean-av#control-system-files)
- [Control System Files Installation](https://github.com/brianlopezpimco/nb03ocean-av#control-system-files-installation)
- [Additional Resources](https://github.com/brianlopezpimco/nb03ocean-av#additional-resources)

## **DSP SYSTEM FILES:**

## **USER INTERFACE EXTENSION FILES:**

### **03-Ocean-A Room Controls: Displays**

![03oceana-displays-pg](/IMAGES/nb03oceana-displays-pg.jpg)

| USER INTERFACE ELEMENT        | WIDGET ID                |
| ----------------------------- | ------------------------ |
| Room Controls Panel           | roomcontrols-pnl         |
| Displays Page                 | displays-pg              |
| Main Display: On Button       | display01-on-btn         |
| Projector: On Button          | display02-on-btn         |
| Projector: Off Button         | display02-off-btn        |
| Projector: Lift Up Button     | display02-liftup-btn     |
| Projector: Lift Down Button   | display02-liftdown-btn   |
| Projector: Screen Up Button   | display02-screenup-btn   |
| Projector: Screen Down Button | display02-screendown-btn |

### **03-Ocean-B&C Room Controls: Displays**

![03oceanb-displays-pg](/IMAGES/nb03oceanb-displays-pg.jpg)

| USER INTERFACE ELEMENT        | WIDGET ID                |
| ----------------------------- | ------------------------ |
| Room Controls Panel           | roomcontrols-pnl         |
| Displays Page                 | displays-pg              |
| Main Display: On Button       | display01-on-btn         |


### **03-Ocean-A&B&C Room Controls: Lighting**

![03ocean-lighting-pg](/IMAGES/nb03ocean-lighting-pg.jpg)

| USER INTERFACE ELEMENT        | WIDGET ID             |
| ----------------------------- | --------------------- |
| Room Controls Panel           | roomcontrols-pnl      |
| Lighting Page                 | lighting-pg           |
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

### **03-Ocean-A&B&C Room Controls: Combine**

![03ocean-combine-pg](/IMAGES/nb03ocean-combine-pg.jpg)

| USER INTERFACE ELEMENT        | WIDGET ID                |
| ----------------------------- | ------------------------ |
| Room Controls Panel           | roomcontrols-pnl         |
| Combine Page                  | combine-pg               |
| Standalone Mode Button        | combine-standalone-btn   |
| Combine Rooms A & B Button    | combine-ab-btn           |
| Combine Rooms B & C Button    | combine-bc-btn           |
| Combine All Rooms Button      | combine-abc-btn          |

## **USER INTERFACE EXTENSION FILES INSTALLATION:**

To upload a user interface extension file; first login to the codec...

![<Login Screen>](/IMAGES/endpoint-login-screen.PNG)

Browse to "User Interface Extensions" from the main menu...

![<User Interface Extensions>](/IMAGES/ui-extension-zoomtools.PNG)

Select hamburger menu at top right, and select "Merge from File". NOTE: If you select "Import from File" any existing UI extensions will be overwitten when the new extension is loaded...

![<User Interface Extensions>](/IMAGES/ui-extension-merge-file.PNG)

Confirm your UI is loaded correctly, and select "Uploade to Device" from the top right menu to push the UI elements to the endpoint...

![<User Interface Extensions>](/IMAGES/ui-extension-loaded.PNG)

## **CONTROL SYSTEM FILES:**

Crestron SIMPL Windows program registers the CP4 with the endpoint for feedback, and maintains "heartbeat" of communication. Widgets from the room controls panel are handled and commands are executed by the applicable module (e.g. cisco-codec, lutron-qs, etc.). 

![simpl-code.png](/IMAGES/simpl-code.png)

**SIMPL+ Codec Module:** Registers codec for feedback and maintains heartbeat...

![simpl-plus-cisco-codec.png](/IMAGES/simpl-plus-cisco-codec.png)

**SIMPL+ Lighting Module:** Handles lighting widgets and executes Lutron lighting controller commands...

![simpl-plus-lutron-qs.png](/IMAGES/simpl-plus-lutron-qs.png)

**SIMPL+ Displays Module:** Handles display widgets and executes Samsung display commands...

![simpl-plus-samsung.png](/IMAGES/simpl-plus-samsung.png)

**SIMPL+ Projector Module:** Handles projector widgets and executes NEC projector commands...

![simpl-plus-nec-projector.png](/IMAGES/simpl-plus-nec-projector.png)

**SIMPL+ Combine Module:** Handles room combine widgets, generates feedback for touch screens, executes biamp DSP presets, and nvx stream locations...

![simpl-room-combine.png](/IMAGES/simpl-plus-room-combine.png)

## **CONTROL SYSTEM FILES INSTALLATION:**

In order to load compiled code to a Crestron processor, you must install Crestron Toolbox. You may need to register with Crestron and request access the software. Once installed, open Toolbox, then open the "Easy Config" tool. (tools menu). Once open, click the pencil at bottom, enter address of processor to connect...

![toolbox-connect.png](/IMAGES/toolbox-connect.png)

Once connected. select the "Program" button. Browse your computer for the file and select send to load the file...

![toolbox-send-code.png](/IMAGES/toolbox-send-code.png)

## **ADDITIONAL RESOURCES:**

- [Cisco Room Controls Design Guide](https://www.cisco.com/c/dam/en/us/td/docs/telepresence/endpoint/ce915/sx-mx-dx-room-kit-boards-customization-guide-ce915.pdf)
- [Cisco RoomOS API References](https://roomos.cisco.com/xapi)
