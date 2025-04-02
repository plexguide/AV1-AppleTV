##### WANT TO HELP? CLICK THE ★ (STAR LOGO) in the Upper-Right! 

# Quick Guide on Enabling Apple TV to Play AV1 Natievly 

What the tvOS.xml profile does. You can see the Apple TV playing AV1 via direct stream, not transcoding from the server

<p align="center">
  <a href="https://i.imgur.com/wPd1pgq.jpeg">
    <img src="https://i.imgur.com/wPd1pgq.jpeg" alt="Logo" style="border: 2px solid #000000; border-radius: 8px; width: 40%;">
  </a>
</p>

## NOTE

I found this script a while ago, and it mentioned that the current Apple TVs (including the most recent models and those just prior) should be fine. However, if you have an older Apple TV, AV1 playback may stutter. I haven't verified this, so it would be helpful if someone could share their feedback after testing the script. It works fine for me.

How to deploy AV1 Transcoding and workflow info? Visit - https://github.com/plexguide/Unraid_Intel-ARC_Deployment

## PayPal Donations – Building My Daughter’s Future

My 12-year-old daughter loves singing, dancing, and exploring STEM. She’s an A-B honor roll student with big dreams for the future. Any donation you make will go directly toward her college fund, helping her turn those dreams into reality. Thank you for your support!

[![Donate with PayPal button](https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif)](https://www.paypal.com/donate?hosted_button_id=58AYJ68VVMGSC)

#### Location

The location of where to put the script is where your plex data is stored and try to find the path until you get to Profiles as seen below. Copy the script and store it as tvOS.xml

```bash
plex/Library/Application Support/Plex Media Server/Profiles/tvOS.xml
```

Make sure to click the copy icon in the upper right so you have an exact copy of what to paste into the tvOS.xml

#### tvOS.xml
```bash
<?xml version="1.0" encoding="utf-8"?>
<Client name="tvOS">
  <TranscodeTargets>
    <VideoProfile container="mkv" codec="h264,h265,hevc,mpeg2video,mpeg4,vc1,av1" audioCodec="flac" subtitleCodec="ass,dvb_subtitle,vobsub,eia_608,pgs,microdvd,movtext,ssa,srt" />
    <MusicProfile container="flac" codec="flac" />
    <PhotoProfile container="jpeg" />
  </TranscodeTargets>
  <DirectPlayProfiles>
    <VideoProfile container="mkv,mov,mp4,mpegts,mpeg,mpegvideo,avi,flv,ogg" codec="h264,h265,hevc,vp9,h263,mpeg1video,mpeg2video,mpeg4,vc1,av1" audioCodec="aac,ac3,alac,flac,eac3,dca,opus" subtitleCodec="ass,dvb_subtitle,vobsub,eia_608,pgs,microdvd,movtext,ssa,srt" />
    <MusicProfile container="mp3" codec="mp3" />
    <MusicProfile container="m4a" codec="aac,alac" />
    <MusicProfile container="mp4" codec="aac,he-aac,ac3,eac3,alac" />
    <MusicProfile container="flac,mkv" codec="flac" />
    <PhotoProfile container="jpeg" />
  </DirectPlayProfiles>
  <CodecProfiles>
  <VideoCodec name="*">
     <Limitations>
       <UpperBound name="video.width" value="3840" />
       <UpperBound name="video.height" value="2160" />
       <UpperBound name="video.bitDepth" value="10" />
     </Limitations>
    </VideoCodec>
    <VideoAudioCodec name="*">
      <Limitations>
        <UpperBound name="audio.channels" value="8" />
      </Limitations>
    </VideoAudioCodec>
  </CodecProfiles>
</Client>
```

<p align="left">
  <a href="https://avatars.githubusercontent.com/u/62731045?s=200&v=4">
    <img src="https://avatars.githubusercontent.com/u/62731045?s=200&v=4" alt="Logo" style="border: 2px solid #000000; border-radius: 8px; width: 8%;">
  </a>
</p>


