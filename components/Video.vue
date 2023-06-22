<template>
    <video ref="videoPlayer" class="video-js" muted></video>
</template>

<script setup>
  import videojs from "video.js";
  import 'video.js/dist/video-js.css'
  import { ref, onMounted } from 'vue'


  const videoPlayer = ref()
  let player = null;
  let qualityLevels = null;
  onMounted(() =>{
    player = videojs(videoPlayer.value, {
      autoplay: false,
      controls: true,
      aspectRatio: '16:9',
      sources: [
        {
          src: 'https://vz-b4f1e97e-483.b-cdn.net/65c65840-de66-4c27-afd0-a3b5a904b768/playlist.m3u8',
          type: 'application/x-mpegURL',
          withCredentials: false
        }
      ],
      controlBar: {
          volumePanel: {inline: false},
          pictureInPictureToggle: true,
      },
      enableDocumentPictureInPicture: false,
      disablePictureInPicture:false,
      html5: {
        nativeAudioTracks: true,
        nativeVideoTracks: true,
        nativeTextTracks: true
      }
      }, function onPlayerReady() {
        console.log('Player is ready!');
    });
  })
</script>

<style lang="scss">
    

.video-js{
  width: 100%;
}


.video-js .vjs-big-play-button {
  position: absolute;
  top: 50%;
  left: 50%;
  height: 3rem;
  width: 3rem;
  transform: -50% -50%;
  border-radius: 9999px;
  border-width: 0;
  --tw-bg-opacity: 1 !important;
  background-color: rgb(71 79 84 / var(--tw-bg-opacity))!important;
  --tw-shadow: 0 1px 3px 0 rgb(0 0 0 / .1), 0 1px 2px -1px rgb(0 0 0 / .1) !important;
  --tw-shadow-colored: 0 1px 3px 0 var(--tw-shadow-color), 0 1px 2px -1px var(--tw-shadow-color) !important;
  box-shadow: 0 0 #0000,0 0 #0000,var(--tw-shadow)!important;

  .vjs-icon-placeholder:before {
    content: "\f101";
    text-align: center;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
}

.video-js .vjs-control-bar{
  background: linear-gradient(180deg,rgba(16,16,16,.02) 0%,rgba(16,16,16,.5) 100%);
}

.video-js .vjs-control{
  width: 4em;
}

.vjs-icon-placeholder:not(.vjs-big-play-button > .vjs-icon-placeholder){
  font-family: kickplayericons!important;
  font-style: normal!important;
  font-weight: 400!important;
  font-variant: normal!important;
  text-transform: none!important;
  line-height: 1!important;
  -webkit-font-smoothing: antialiased!important;
  -moz-osx-font-smoothing: grayscale!important;
}

.vjs-icon-picture-in-picture-enter:before, .video-js .vjs-picture-in-picture-control .vjs-icon-placeholder:before{
  content: "\f121" !important;
}
.vjs-control:hover {
    --tw-text-opacity: 1;
    color: rgb(83 252 24 / var(--tw-text-opacity));
}

.video-js *:not(.vjs-visible-text)>.vjs-control-text{
  border: 0;
    clip: rect(0 0 0 0);
    height: 1px;
    overflow: hidden;
    padding: 0;
    position: absolute;
    width: 1px;
}

.vjs-control-text {
    font-family: Inter,ui-sans-serif,system-ui,-apple-system,BlinkMacSystemFont,Segoe UI,Roboto,Helvetica Neue,Arial,Noto Sans,sans-serif,"Apple Color Emoji","Segoe UI Emoji",Segoe UI Symbol,"Noto Color Emoji";
    top: -1.5rem!important;
    left: 50%!important;
    z-index: 50!important;
    display: none!important;
    height: -moz-fit-content!important;
    height: fit-content!important;
    width: -moz-fit-content!important;
    width: fit-content!important;
    --tw-translate-x: -50% !important;
    transform: translate(var(--tw-translate-x),var(--tw-translate-y)) rotate(var(--tw-rotate)) skew(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y))!important;
    white-space: nowrap!important;
    border-radius: 0.125rem!important;
    background-color: #191b1fb3!important;
    padding: 0.375rem!important;
    vertical-align: middle!important;
    font-size: .75rem!important;
    line-height: 1rem!important;
    font-weight: 500!important;
    line-height: 1!important;
    --tw-text-opacity: 1 !important;
    color: rgb(255 255 255 / var(--tw-text-opacity))!important;
    clip: auto!important;
}

.vjs-control:not(.vjs-menu-button,.vjs-progress-control,.vjs-volume-control,.vjs-volume-panel-vertical):hover .vjs-control-text {
    display: block !important;
}






</style>