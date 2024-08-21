##### WANT TO HELP? CLICK THE ★ (STAR LOGO) in the Upper-Right! 

# Quick Guide on Enabling Apple TV to Play AV1 Natievly 

<p align="center">
  <a href="https://avatars.githubusercontent.com/u/62731045?s=200&v=4">
    <img src="https://avatars.githubusercontent.com/u/62731045?s=200&v=4" alt="Logo" style="border: 2px solid #000000; border-radius: 8px; width: 10%;">
  </a>
</p>

## PlexGuide Information - About the Main Project (Unraid Script Info Below)

```bash
sudo apt-get update -y && sudo apt-get install -y curl git && curl -o /tmp/install.sh https://raw.githubusercontent.com/plexguide/PlexGuide.com/v11/mods/install/install.sh && chmod +x /tmp/install.sh && /tmp/install.sh && chmod +x /pg/scripts/menu.sh && /pg/scripts/menu.sh
```

* Simple, debloated, no fancy menus and executes for exactly what you need and works for Ubuntu 22 and Ubuntu 24 Server LTS
* Once installed, type `pg` or `plexguide`

<p align="center">
  <table align="center">
    <tr>
      <td align="center"><img src="https://i.imgur.com/tuJpsTR.jpeg" alt="Menu Example" width="500"></td>
      <td align="center"><img src="https://i.imgur.com/M7G2LLl.jpeg" alt="Plex Example" width="500"></td>
    </tr>
    <tr>
      <td align="center"><img src="https://i.imgur.com/goozBTI.jpeg" alt="Plex Example" width="500"></td>
      <td align="center"><img src="https://i.imgur.com/WkEyL9D.jpeg" alt="Plex Example" width="500"></td>
    </tr>
  </table>
</p>

## NOTE

I found this script somewhere random way back, but it warned that the current apple tv (most recent and prior are fine), but if you have the old apple tv's, AV1 may stutter. I have no verified this and would be helpful if someone post in dicussion their feedback in testing this script. It works fine for me.

## SCRIPT

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





