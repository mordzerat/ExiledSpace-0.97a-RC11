Link for guide can be found on discord
Invite link : https://discord.gg/a8AWVcPCPr
Readme link : https://discord.com/channels/187635036525166592/512356777451323393/894702930987466852

Mini-guide: Switching to Java 8 to prevent the post-battle slowdown
Help me help Alex by testing a new JRE 8.

Symptoms
After some time playing and immediately after a battle, the game FPS will plummet (eg from 60 to 15-25) and usually only go back to normal after a game restart.
Saving/loading takes 5x longer than usual.
Using at least one mod (that adds new sprites? incl. GraphicsLib).
Crash mentioning "PermGen space".

Instructions: (slow down and read this part carefully)

Windows users:
Go to your Starsector install and rename the jre folder to jre-backup.
Download (37 MB) https://github.com/wispborne/JRE/releases/download/jre8-362-azul/JRE_8_research.zip.
Extract that somewhere, then drag jre into your Starsector folder. You'll now have both jre (with java 8) and jre-backup.
See this image for the correct jre path: https://i.imgur.com/yZj5A1C.png
Replace your vmparams file with one of the ones included in the download, based on how much RAM you want to allocate (see ⁠troubleshooting to determine that, but don't download those files, they won't work for this JRE without -Xverify:none).OR edit your own vmparams file to add  -Xverify:none  (with spaces around it) immediately after java.exe (ie at the front).
Read the Potential Issues section below (your game+launcher may be zoomed in/off-center).
React with :bugdog: so we have an idea of how many people are testing.
Launch the game as normal.


Mac/Linux users:
Go here (https://www.azul.com/downloads/?version=java-8-lts&os=macos&architecture=x86-64-bit&package=jre#zulu), 
 pick your Operating System, and download.
Follow the Windows steps above, but with the following changes:
2a. Rename the JRE folder you downloaded from the azul.com site.
   MacOS users: rename the new jre folder to Home. The one you need to replace is in Starsector.app/Contents (right-click Starsector and Show Package Contents).
   Linux users: rename the new jre folder to jre_linux and replace the existing one.
2b. Instead of editing/replacing vmparams, you will need to edit your .sh file. Easiest is to open it in an editor and copy another line with -X in it, paste it after the java.exe line, and edit it to -Xverify:none.
React with :bugdog: so we have an idea of how many people are testing.

Potential issues
Game+launcher is zoomed in/off-center.
  This should no longer happen. Please let me know if it still does.

java.exe error message
  Do step 4 in the above instructions. If you're sure you have, make sure your antivirus didn't eat jre/bin/java.exe or jre/bin/javaw.exe.