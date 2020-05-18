## How to Use FFmpeg to Combine Covert Art with Podcasts For Upload to YouTube

Published in: [TheLinuxOS.com](https://thelinuxos.com/use-ffmpeg-upload-podcasts-youtube/)

![](/images/linux1.png)

If you’re involved in producing a podcast, then you’re probably interested in using syndication channels and other services to maximize your show’s reach. 

One channel that people tend to gloss over for audio podcasts is YouTube. But podcasters around the world are uploading audio podcasts with static images to boost their reach and build their following for when the podcast is ready to integrate a video dimension.

Of course, combining audio and an image file to produce a video clip can be achieved using just about any video editing GUI for Linux. Openshot, Handbrake, and Lightworks are all popular choices. But in reality, the well-known command-line interface (CLI) FFmpeg is all that’s needed to get the job done. 

Here’s what you need.

Ready Your Files
For this example, I’m assuming that you simply want to overlay a static image for the duration of your podcast. 

Firstly, you’ll need to design an image for your target video format’s resolution. I created my artwork in 1080p (Full HD). Its pixel dimensions are 1920 x 1080.

Next, you’ll want to get the audio track of your podcast ready. 

## Run FFmpeg

Once you have your files ready, it’s time to run an FFmpeg command.  

There are many different possibilities here. But the command I had success with was: 

```
ffmpeg -r 1 -loop 1 -y -i cover_art.png -i audio.m4a -c:a copy -r 1 -vcodec libx264 -shortest podcast.avi
```

Several other options I tried failed to pass YouTube processing. 

![](/images/podcasts1.png)

In truth, your output format could be any format that YouTube accepts for uploads. These include:

.3gpp
.avi
.flv
.mov
.mp4
.wmv
Let’s break down that command. The full FFmpeg documentation can be found here.

```
ffmpeg -r 1 -loop 1 -y -i cover_art.png -i audio.m4a -c:a copy -r 1 -vcodec libx264 -shortest podcast.avi
```

‘Ffmpeg’ calls the FFmpeg CLI.
 

**-r**. This option sets the frame rate in frames per second (fps), which refers to the frequency at which the frame is refreshed. Because we’re simply showing one image throughout the duration of the podcast video, we can set this to 1 in order to significantly reduce file size and speed up the processing time. For real video projects, frame rates are typically between 24 and 60 fps. <br/>
**-loop**. We use this option to ensure that the first use of -i, which calls the cover art, streams for the entire duration of the corresponding audio track. <br/>
**-i**. This is the input source option. We provide the path to the “video” first, which is the covert art, and add the audio track second. <br/>
**“-c:a copy -r 1”.** This part of the command sets that the audio file will be copied as is into the output without any transcoding. <br/>
**“-vcodec libx264”.** This part of the command sets that the video component of the file, which is our static PNG image, will be encoded using libx264. <br/>
**“-shortest”.** This part of the command tells the CLI to finish encoding when the shortest input stream ends.  <br/>

The last part of the command is the output file type.

I used this process to convert a roughly 30-minute podcast file in under three minutes. And the file that resulted was just under 40 Megabytes. I found this quicker and easier than using Openshot and it resulted in a lighter file.

Use this method the next time you want to upload your podcast as a “video” file on YouTube.
