# Asterisk VoIP Lab Project

## General Description

This project was developed as part of a communications networks lab, with the goal of configuring and simulating a VoIP (Voice over IP) telephony system using the **Asterisk** server. It allows for calls between SIP and IAX users, includes a call queue system, echo testing, and playback of audio messages or music on hold.

## Technologies Used

- **Asterisk PBX** (Private Branch Exchange)
- Protocols: **SIP**, **IAX2**
- Configuration via `.conf` text files
- Interactive features: echo test, audio playback, music on hold, agent login

## Project Structure

### 1. `sip.conf`
Defines SIP users and their parameters:
- Users: `1000`, `1143`, `2143` – each assigned to specific contexts with video support
- Supported codecs: `ulaw`, `alaw`, `gsm`, `ilbc`, `h264`, `h263`

### 2. `iax.conf`
Defines IAX users such as `2000`, `3143`, `4143`, each with its own context and password authentication.

### 3. `extensions.conf`
Main dialplan configuration file:
- `internal` context – enables calls to SIP/IAX extensions
- `public_category3` context – handles agent login and call queue
- `sipfunc` and `iaxfunc` contexts – provide audio playback, test tones, and functionalities like `Echo`, `SayDigits`, `SayNumber`

### 4. `musiconhold.conf`
- Configures music on hold, using files located in `/var/lib/asterisk/moh/music`
- To ensure music is played correctly, you need to include the audio file `custom.wav` in that directory

### 5. `indications.conf`
Defines tones and frequencies specific to a region.

## Features

- Audio and video calls between SIP and IAX users
- Testing features (echo test, digit/letter playback, time announcement)
- Customizable music on hold
- Agent login and call queue management

## File Structure

<pre>
src/
├── extensions.conf      # call logic and routing
├── sip.conf             # configuration of SIP users
├── iax.conf             # configuration of IAX2 users
├── musiconhold.conf     # music on hold settings
├── indications.conf     # regional tone configuration
├── custom.wav
</pre>

## Disclaimer

This project was created as part of an academic assignment. Feel free to use it for learning purposes, but please do not submit it as your own work in educational settings.
