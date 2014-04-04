Prompter
========

### HTML5 Text Prompter for Audio Recording


### Javascript Teleprompter Recording App for HTML Documents

This is a simple Javascript web app HTML document viewer which adds two features: 

1) Teleprompter style scrolling and 
2) Block-level HTML5 audio recording, saving recorded audio in a local data store
3) Data is synced to a remote database 
4) Login is based on user/password accessing remote database at least once


### Teleprompter libraries are available off-the-shelf such as: 

http://jscroll.com/ (endless scrolling)
http://www.javascriptsource.com/miscellaneous/teleprompter.html 

### Interface concept: look at this teleprompt app: simple and easy to read:
https://itunes.apple.com/us/app/teleprompt+-for-ipad/id364903926?mt=8

### A jQuery plugin for audio recording:

http://www.sajithmr.me/jrecorder-jquery

### Database connectors for local data and PouchDB:

PouchDB: https://github.com/daleharvey/pouchdb
Backbone connector for PouchDB: https://github.com/jo/backbone-pouch

* App takes a URL to provide HTML file to be read, keeps the file for later
    * Suggstion: on load, break up file into sequential records in the local database
    * Then attach audio to each record as it is complete
    * Allow PouchDB/CouchDB to manage syncing up these records
    * Each record should have the original URL, reader username, block ID, sequence #, and text to be read

* Document auto-scrolls and displays like a teleprompter
    * User can scroll up or down, starting reading from any block
    * Use Jquery or similar technique to insert playback controls into each block (subtle please)
    * Record content of each block-level HTML element (div, p, h# etc.), at the end of each block prompt for re-record or audio save

* User should provide login credentials which must access remote db access (since there is no server side role for this app). User credentials are stored locally so user does not have to re-login each time

* User should be able to stop at the end of any block and resume later.

* User should be able to listen to any recorded block and re-record or start recording at any block in the document.
    * re-recording just replaces record with a new version of the same record

* Remote DB settings and recording settings (gain, bitrate) should JS config file controlled by developer (not end user)

* Application should use a backbone.js/marionette.js approach but need not use Require.js or any other AMD


