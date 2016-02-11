<!--
# license: Licensed to the Apache Software Foundation (ASF) under one
#         or more contributor license agreements.  See the NOTICE file
#         distributed with this work for additional information
#         regarding copyright ownership.  The ASF licenses this file
#         to you under the Apache License, Version 2.0 (the
#         "License"); you may not use this file except in compliance
#         with the License.  You may obtain a copy of the License at
#
#           http://www.apache.org/licenses/LICENSE-2.0
#
#         Unless required by applicable law or agreed to in writing,
#         software distributed under the License is distributed on an
#         "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
#         KIND, either express or implied.  See the License for the
#         specific language governing permissions and limitations
#         under the License.
-->

# cordova-plugin-media-with-setAudioStreamType

Fork of Media plugin with adding ability to change media play type: Ring, Music, Notification, system


This plugin provides the ability to record and play back audio files on a device.


## Supported Platforms

- Android
- Browser

## Stream Types avialable 
*notification
*alarm	(The audio stream for alarms)
*dtmf	(The audio stream for DTMF Tones)
*music	(The audio stream for music playback
*notification (The audio stream for notifications)
*ring	(The audio stream for the phone ring)
*system	(The audio stream for system sounds)
*voice_call
## Example 

    var media = new Media(src, mediaSuccess, [mediaErrorCB], [mediaStatusCB], streamType); 
    //or
    Media.streamType ="music";
	
### Parameters

- __src__: A URI containing the audio content. _(DOMString)_

- __mediaSuccess__: (Optional) The callback that executes after a `Media` object has completed the current play, record, or stop action. _(Function)_

- __mediaError__: (Optional) The callback that executes if an error occurs. _(Function)_

- __mediaStatus__: (Optional) The callback that executes to indicate status changes. _(Function)_
- __streamType__: (Optional) StreamType setting. _(String)_

__NOTE__: `cdvfile` path is supported as `src` parameter:
```javascript
// Avialable stream types:
//notification
//alarm	(The audio stream for alarms)
//dtmf	(The audio stream for DTMF Tones)
//music	(The audio stream for music playback
//notification (The audio stream for notifications)
//ring	(The audio stream for the phone ring)
//system	(The audio stream for system sounds)
//voice_call

//OPTION 1:  You should call setStreamType before create an media object
Media.setStreamType ="music";
var my_media = new Media('cdvfile://localhost/temporary/recording.mp3', ...);

//OPTION 2: You can set streamType by type paramert of constructor 

var my_media = new Media('cdvfile://localhost/temporary/recording.mp3', ..., "music");

// OPTION 3: You can set StreamType by calling  mediaObject.setAudioStreamType(type) methon BEFORE call play() method;
var my_media = new Media('cdvfile://localhost/temporary/recording.mp3', ...);
 my_media.setAudioStreamType("system");
 my_media.play();
```

###install
PhoneGap build or Cordova cli:  <plugin name="cordova-plugin-media-extended" source="npm" version="2.2.3"></plugin> (add to config.xml)


## all others features one by one forked from cordova-plugin-media 2.2.1

 
