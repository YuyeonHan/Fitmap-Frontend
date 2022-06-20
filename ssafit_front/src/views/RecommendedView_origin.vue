<template>
  <div class ="container">
      <div class="header">
        <vuejs-heatmap :entries="entries"></vuejs-heatmap>
      </div>
      <div class = "container" id="recommend_comment" style="text-align : left">
        <div><p class="slide_title">
            <strong >
              {{this.$store.getters.GET_USERID}}님, 좋은 {{time}}입니다.
            </strong>
          </p>
					<p class="slide_text">
            <span>
              최근 3일의 기록에 따르면 오늘은 <span class="highlight">{{this.$store.getters.GET_RECPART}} </span>운동이 필요한 날입니다.
            </span>
          </p>
        </div>

			</div>

    <div class ="card" style="width: 18rem;" v-for ="(video, index) in recommendedVideos" :key="index">
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
import VuejsHeatmap  from '@/components/common/VuejsHeatmap'

export default {
  data(){
    return{
      time : '',
    }
  },
  components: {
    VuejsHeatmap,
  },
  computed:{
    ...mapState([
      'recommendedVideos',
      'ENTREIS'
      
    ])
  },
  created(){
    this.$store.dispatch('getRecordWithEntries');  
     this.$store.dispatch('recommendVideo')
     let now = new Date().getHours();
     if(now<11){
       this.time = '아침'
     }else if(now <14){
       this.time = '점심'
     }else if(now <17){
       this.time = '오후'
     }else{
       this.time = '저녁'
     }
    
  }
  ,
  methods:{
    addlike(videoID){
    const params={
      likeId: 0,
      userId: this.$store.getters.GET_USERID,
      videoId: videoID,
    }
      alert('찜목록에 추가했습니다.')
      this.$store.dispatch('addLikeVideo', params)
    }
    }
    

}
</script>

<style scoped>

  .card{
    margin: 10px;
    width: 100vh;
    
  border-radius: 5px;
  background-color: rgb(236, 231, 224);
    }

  .container{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
  }
  span.highlight {
    color: rgba(220, 51, 51, 0.865);
  }

  #recommend_comment{
    font-size : 30px;
  }
  #explanation{
    font-size : 20px;
  }
</style>
