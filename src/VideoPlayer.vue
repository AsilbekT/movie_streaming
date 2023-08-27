<template>
    <div>
        <video ref="videoPlayer" class="video-js"></video>
    </div>
</template>

<script>
import videojs from 'video.js';
import 'video.js/dist/video-js.css';

export default {
    props: ['src'],
    mounted() {
        const player = videojs(this.$refs.videoPlayer, {
            controls: true,
            autoplay: true,
            preload: 'auto',
        });

        player.src({
            src: this.src,
            type: 'application/x-mpegURL',
        });
    },
};
</script>

<style>
/* Add any additional styling for the video player here */
</style>
