<template>
  <div>
    <video ref="videoPlayer" class="video-js"></video>
  </div>
</template>

<script>
import 'video.js/dist/video-js.css';
import videojs from 'video.js';

export default {
  mounted() {
    const player = videojs(this.$refs.videoPlayer, {
      controls: true,
      autoplay: false, // Disable autoplay
      muted: true, // Mute the video initially if desired
      sources: [
        {
          src: 'http://127.0.0.1:7007/videos/master.m3u8',
          type: 'application/x-mpegURL',
        },
      ],
    });
    player.play();

    // You could add a play button and use player.play() when it's clicked
  }

};
</script>
