/**
 *  Plex Communicator Device
 *
 *  Copyright 2018 Jake Tebbett (jebbett)
 *
 *  Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except
 *  in compliance with the License. You may obtain a copy of the License at:
 *
 *      http://www.apache.org/licenses/LICENSE-2.0
 *
 *  Unless required by applicable law or agreed to in writing, software distributed under the License is distributed
 *  on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License
 *  for the specific language governing permissions and limitations under the License.
 *
 * 2018-11-17	2.0		Updated to report playbackType Correctly
 * 2020-05-24   2.1    Updated to add track title
 */

metadata {
	definition (name: "Plex Communicator Device", namespace: "jebbett", author: "jebbett") {
	    capability "Music Player"
	    attribute "playbackType", "string"
	    attribute "status", "string"
        attribute "trackDescription", "string"
	}
}

// External
def playbackType(type) {
	sendEvent(name: "playbackType", value: type);
    //log.debug "Playback type set as $type"
}

def setPlayStatus(status){
    // Value needs to be playing, paused or stopped
    sendEvent(name: "status", value: status)
	log.debug "Status set to $status"
}

def setTitle(title) {
	sendEvent(name: "trackDescription", value: title);
    //log.debug "Title set as $title"
}

def play() {	        
    sendEvent(name: "status", value: "playing");
}

def pause() {
    sendEvent(name: "status", value: "paused");
}

def stop() {
    sendEvent(name: "status", value: "stopped");
}