<template>
  <div class ="container">
      <div class ="card" style="width: 18rem;"
      v-for ="(video, index) in resultVideos" :key="index">
        <iframe :src='`https://www.youtube.com/embed/${video.videoId}`'></iframe>
        <div  class="card-body">
          <p class="card-text">{{video.title}}</p>
          <button  @click="addlike(`${video.videoId}`)">찜</button>
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
  created(){
   this.$store.dispatch("searchPartVideo", 3)
  },
  methods: {
    addlike(videoID){
    
    const params={
      likeId: 0,
      userId: this.$store.getters.GET_USERID,
      videoId: videoID,
    }
    alert('찜목록에 추가했습니다.')
      this.$store.dispatch('addLikeVideo', params)
    },
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
