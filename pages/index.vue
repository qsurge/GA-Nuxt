<template>
  <div>
    <video 
    id= "video-player"
    class="cld-video-player"
    >
    </video> 
  </div>
</template>


<style scoped>

 div{
  display: flex;
  align-items: center;
  justify-content: center;
}
.cld-video-player{
  width: 500px;
  height: 500px;
}

</style>

<script>

export default {
  data(){
    return{
      cld: null,
      player: null,
      video: "production_ID_4456999_gr6iy4"
    }
  },
  mounted(){
    this.cld= cloudinary.Cloudinary.new({
      cloud_name:  'amarachi-2812',
      secure:  true
    })
    this.player = this.cld.videoPlayer(
      'video-player', {
        controls: true,
        analytics: {
          events: [
            'play',
            'pause',
            'ended'
          ]
        }
      }
    );
    this.player.source(this.video);
}

}


</script>

