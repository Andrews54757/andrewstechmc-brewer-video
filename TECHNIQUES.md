# Special Techniques

## "3d" Text/info

<img width="509" alt="Screen Shot 2021-02-20 at 10 49 39 PM" src="https://user-images.githubusercontent.com/13282284/108615057-2966eb00-73ce-11eb-9c8b-6920216c9b65.png">

This was done with planar tracking in Resolve's Fusion tab. I used [this](https://www.youtube.com/watch?v=aJaGZ2a2BwQ) nice tutorial to learn how to do this.

However, not all surfaces are trackable. For example, you can't track air, nor can you track glass nicely. So, here is a technique I used to be able to do so:

1. Create a short replay with patterned blocks where you want to track (`Track.mcpr`).
2. Copy and paste the timeline from the main replay into this new one.
3. Render with ReplayMod. (can be low graphics setting for fast rendering)
4. Right click on clip you want to track in resolve, select "Replace Clip"
5. Replace clip with the track-video. Then track as you normally would.
6. Once your satisfied with your tracking, replace the clip back to the original.
7. The tracking data will persist. Yay!

## Transparent Blocks Effect

<img width="433" alt="Screen Shot 2021-02-20 at 10 50 14 PM" src="https://user-images.githubusercontent.com/13282284/108615056-2966eb00-73ce-11eb-9422-f08596400895.png">

Normally, this is a difficult effect to pull off as traditionally, you would have to do it "manually" by either seperating your contraption to seperate groups, or using a texture pack. Not only is it difficult, it is also pretty limiting (ie, you can't do the effect to moving things like slimestone, and entities are hard to overcome).

As a result, I ended up just programming a new feature called `selectiveBlocksRendering` in [Tweakfork](https://github.com/Andrews54757/tweakfork). With this, you can make blocks selectively render/not render, depending on the positions you add in the white/blacklists. It also is able to track piston movements and update the lists accordingly, so doing this effect on slimestone is now possible.

Fun fact: This feature was the main reason why I decided to make the potion video. DesktopFolder needed the mod for rendering the [3 way bedrock breaker video](https://www.youtube.com/watch?v=kTRjq0kCfHU) and I needed motivation to actually make it.

## Codecs

<img width="508" alt="Screen Shot 2021-02-20 at 10 51 05 PM" src="https://user-images.githubusercontent.com/13282284/108615055-28ce5480-73ce-11eb-80a7-2f2b8e8bac57.png">

Youtube, by default, re-encodes all videos to avc1. This results in grainy videos sometimes, which is unacceptable when you have shadows in your video. However, some videos are encoded to vp09 which has higher quality compression. But, you can't choose what codec you want to use when uploading to youtube and the conditions for that are not documented.

As of Feb 20, 2021, this is the technique for making youtube use the vp09 codec:
1. Render your video in 4k, upscale it if you need to and use mp4 format
2. Wait for youtube to finish re-encoding HD and 4k resolutions. It may take a while for that to finish and during that time you will have avc1 codec only.
3. Once its done, verify that the codec is indeed vp09 by watching the video, right clicking on the video, and selecting "Stats for Nerds"

#### Side comment: Though I was successfully able to make youtube use the vp09 codec, on viewing I can't really notice the quality differences - both still have horrible compression but vp09 is slightly better i guess? Here is av1c version of the video if you want to compare: [av1c (unlisted)](https://youtu.be/o8Sc87yCAnk) [vp09 (published)](https://youtu.be/1_jSkyq-WOs)
