# Plex Communicator V2.0

**Using Plex Webhooks, a custom Plex2Hub program or some dodgy polling from your chosen smart home platform this provides you a device that you can then control your lights etc in response to what's being played on Plex**

This will not provide control of Plex, but will give you the current state, type of media and media title of each of your plex devices.

### Instructions

Note: (Hubitat files are in the Hubitat folder)

1. Install the App and enable OAuth
2. Install the Driver (Hubitat) / Device Hander (SmartThings)
3. Run the app, you will need ot login and add the LAN IP of your plex server
4. Select your devices and these will appear where they should
5. Setup your "Connection Method", taking the information required from the Plex Communicator App
6. Enjoy

### For lighting control

Use the automation in build to your hub or use MediaScene by me (You'll need to use search until I release it properly)

### Errors / Debugging

**Plex2Hub.exe - SendGetRequest: the remote server returned and error: (403) Forbidden**
There is an issue with the URL in config.config re-check section 2.D

**No error in the EXE and nothing appearing in your smart home logging (with logging turned on)**
This is because your hub is not receiving an event, this is usually because the App ID or Token are incorrect, if you re-install the app these values will change and need to be setup again.

**Live Logging - java.lang.NullPointerException: Cannot get property 'authorities' on null object @ line xx**
You have not enabled OAuth in the parent app

### GitHub
https://github.com/jebbett/Plex-Communicator