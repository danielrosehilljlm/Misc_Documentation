## Using xdotool, at, and Bash to automate Netflix and YouTube viewing on Linux

![](/images/21.png)

What could be better than wrapping up a hard day at work with a few hours of Netflix and chilling?

How about having your home media center doing all the hard work for you: opening your favorite show, hitting the resume button, and even turning on closed captions if you so desire.

All you need to do at the appointed hour is plonk yourself on the couch!

Here’s how easy it is to set that up:

All it takes to get that up and running is some very elementary Bash scripting know-how, the xdotool command line interface (CLI), and the ‘at’ CLI to schedule once off jobs at your preferred Netflix-and-chilling time (for more detail on how to get ‘at’ working check out the man page here).

In the above screencast I demonstrated how you can use xdotool and a simple Bash script to:

Open, in Google Chrome (or your browser of choice) the media file / YouTube video / Netflix series you wish to view.

Find the coordinates for any buttons that you need to press. In the demonstration script I used simulated mouse clicks to play the video, turn on captions, and enter full screen mode.
Simulate a keystroke.

You can even include an ‘at’ command within the Bash script itself to turn the whole system off (or run another script) after a designated period. This will allow your system to gracefully shut itself down upon your movie’s conclusion.

[YouTube video](https://www.youtube.com/watch?v=dXHdpz9QA7M&feature=emb_title)

```
## Example Bash script for automatically launching and resuming a Netflix series

#!/bin/bash
# A bash script for launching 'Shtisel' in Netflix
# By: Daniel Rosehill / DanielRosehill.co.il
#
# Call arandr script to pipe output to HDMI (TV)
/bin/bash /home/daniel/TV_only.sh 
# Unmuting volume and then setting it to 100%
amixer sset Master unmute 
amixset sset Master 100% 
# Open 'Shtisel' series page in Netflix
echo "Opening Shtisel page on Netlix" 
google-chrome https://www.netflix.com/title/81004164 
sleep 5 
# Click the resume button
xdotool mousemove 115 531 
xdotool click 1 
# Wait five seconds and then make full screen
sleep 5 
xdotool mousemove 1857 991 
sleep 3h
sudo poweroff
exit
```
