<template>
<div><ul class="movie-list" >
        <li v-for="subject in moveList" :key="subject.id" class="movie"> 
                 <div class="movie-img">
                     <img :src="subject.images.small.replace('https','https://images.weserv.nl/?url=https')">
                 </div>
                 <div class="movie-info">
                <p class="movie-name">中文名：{{subject.title}}</p>
                <p>外文名：{{subject.original_title}}</p>
                <p>创作时间：{{subject.year}}</p>
                <p>主题：{{subject.genres[0]}} {{subject.genres[1]}}</p>
            </div>
     
        </li>
    </ul>
    <div class="loading" v-show="loadingShow">
        <img src="../../assets/img/loading.gif" alt="">
    </div>

</div>
</template>

<script>
import Axios from 'axios'
export default {
    data(){
      return {
          moveList: [],
          loadingShow: true
      };
    },
    mounted() {
      Axios.get(API_PROXY + "https://douban.uieee.com/v2/movie/in_theaters?count=20&start=0")
      .then(res => {
          console.log(res);
          this.loadingShowing=false;
          this.moveList = res.data.subjects;
      })
      .catch(() => {});
    }
  
};
</script>

<style scoped>
.movie{
    display: flex;
    padding: .2rem;
    border-bottom: 1px soli red;
}
.movie-img{
    flex-grow: 1;
    width: 0%;
    margin-right: .2rem;
}
.movie-img img{
    width: 100%;
    height: 100%;
    
}
.movie-info{
    flex-grow: 2;
    width: 0%;
    font-size: 35%;
    line-height: 0.6rem;
}
.movie-list{
    margin: 1rem 0;
}
.movie-name{
    font-weight: normal;
}
.loading{
    text-align: center;
}
</style>