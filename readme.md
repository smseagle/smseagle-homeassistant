<h1>SMSEagle configuration</h1>

Here is a sample configuration to send SMS texts or make a call (ring or text-to-speech) from Home Assistant.

<h3>Requirements:</h2>

You need to have an SMSEagle hardware SMS gateway ([smseagle.eu](smseagle.eu)).

<h2>Setup:</h2>

1. SMSEagle setup
   - Login to webGUI of your SMSEagle device
   - Go to menu **Users > Access to API**
   - Enable **APIv2** and generate new API **access token**
   - In permissions enable: **Send SMS (single recipient), Make a ring call, Make a TTS Advanced call**


2. Home Assistant setup
   - Open file configuration.yaml (located in your HomeAssistant /config folder)
   - Add the lines from configuration.yaml file from this repository
   

3. Replace **IP.OF.YOUR.SMSEAGLE** with IP of your SMSEagle device
4. Replace **YOUR-API-ACCESS-TOKEN** with actual access token from setup

<h2>Usage:</h2>

To send SMS from Home Assistant:
- Select action **"Notifications: Send a notification with send_sms"**
- In field message type your SMS text
- Check field "data" and enter: `number: RECIPIENT_PHONE_NUMBER`

To make a call (text-to-speech) from Home Assistant:
- Select action **"Notifications: Send a notification with make_tts_call"**
- In field message type your text
- Check field "data" and enter: `number: RECIPIENT_PHONE_NUMBER`

To make a ring-only call from Home Assistant:
- Select action **"Notifications: Send a notification with make_a_call"**
- In field message type: **Ring** 
- Check field "data" and enter: `number: RECIPIENT_PHONE_NUMBER`