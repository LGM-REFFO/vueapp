<template>
    <div class="detail">
        
    </div>

</template>

<script>
import Axios from 'axios'
export default {
    data(){
        return {
            detail: {}
        };
    },
    mounted(){
        let url = API_PROXY + "https://api.douban.com/v2/movie/subject/" + this.$rouet.params.movieId;
        Axios.get(url).then(res => {
            //this.detail = res.data.subject
            console.log(res);
        });
    }
};
</script>

<style scoped>


</style>