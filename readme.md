#!WebM.y.TsM's WebM Converter
This is a simple wrapper for [FFmpeg](http://www.ffmpeg.org/download.html) to create WebM files. My version is generally among the best, due to my experience with encoding videos for years. To download it, please click [here](https://github.com/MasterOfWebM/WebM-Converter/releases/download/v0.1.4/Release.zip), [here](https://github.com/MasterOfWebM/WebM-Converter/releases/download/v0.1.4/Release.zip), or [here](https://github.com/MasterOfWebM/WebM-Converter/releases/download/v0.1.4/Release.zip).

Make sure that you have your own FFmpeg in the root directory of the program, otherwise nothing will happen. Better yet, it should be within your System Variable, but whatever.

##What can it do?
This is what she looks like:

![alt text](http://i.imgur.com/0mE0VvV.png)

Currently it can only:

* Automatically calculate the bitrate needed (3MB (Which doesn't work for all boards, like /b/))
* Scale the video
* Seek to a custom time

##Why only offer 2-pass?
Currently it is only offered since this is designed as a GUI for 4chan users. 2-pass encoding will look better than crf with q-min/max 95% of the time, since 2-pass is designed to get the best quality for a given size. In the future, I wish to make a complete WebM wrapper, and even maybe a complete FFmpeg wrapper.

##Can you explain what the weird flags are?
Sure!

* -quality best: Should be obvious. You can use "-quality good -cpu-used 0" to speed it up, but the results will looks worse.
* -slices 8: Slices make the encoder cut the individual frames into the amount of slices (1, 2, 4, & 8 are possible). Generally 4 is good enough for 720p content. Slices slightly increase the quality of each frame.
* -auto-alt-ref 1: This enables the encoder to look into the future instead of just the past, or "Golden Frame". This can increase the quality drastically, or severly hurt it. It works 99% of the time, so I just leave it on.
* -lag-in-frames 16: This is amount of frames it can look into the future. The limit is around 25, but 16 seems to be the best quality/speed tradeoff point on lower-end machines.

##Why a speaker icon?
Irony.

##What is planned?
Plenty of stuff is planned:

* Ability to use subtitles
* Input custom size restriction
* Check the size of the outputted video to see if it worked properly
  * If it didn't, then give recommendations to the user to fix it
* Update check
* Drag and Drop
* Plenty of more stuff

##License
The code is released under [the GPLv2 license](http://www.gnu.org/licenses/gpl-2.0.html).