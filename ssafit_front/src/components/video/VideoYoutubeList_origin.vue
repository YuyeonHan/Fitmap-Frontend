<template>
  <div class ="container">
      <div class ="card" style="width: 18rem;"
      v-for ="(video, index) in resultVideos" :key="index">
        <iframe :src='`https://www.youtube.com/embed/${video.id.videoId}`'></iframe>
        <div  class="card-body">
          <p class="card-text">{{video.snippet.title}}</p>
          <button  @click="addlike(video)">찜</button>
        </div>
      </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  computed:{
    ...mapState([
      'resultVideos'
    ])
  },
  methods:{
    addlike(video){
      console.log("영화 찜")
      console.log(video)
      const params={
        likeId: 0,
        userId: this.$store.getters.GET_USERID,
        videoId: video.id.videoId,
      }
      const videoInfo={
       
        videoId: video.id.videoId,
        title : video.snippet.title,
        part : 4, //여기
        channel : video.snippet.channelTitle,
        url : "https://www.youtube.com/embed/"+video.id.videoId

      }

      alert('찜목록에 추가했습니다.')
      this.$store.dispatch('addVideo', videoInfo);
      this.$store.dispatch('addLikeVideo', params)
    }
  }
}
</script>

<style scoped>
.card{
  margin: 10px;
  width: 300px;
  
border-radius: 5px;
background-color: rgb(236, 231, 224);
  }

.container{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
}


</style>
