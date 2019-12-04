<template>
    <div class="header">
        <button class="home">首页</button>
        <h4 class="title">Movie</h4> 
    </div>

</template>

<script>
export default {
    
}
</script>
<style scoped>
.header{
    height: 1rem;
    background-color: rgb(33, 150, 243);
    position: fixed;
    top: 0;
    width: 100%;
    line-height: 0.5rem;
}
.home{
    color: #fff;
    border: 0; 
    outline: none;
    background-color: transparent;  
}
.title{
    position: absolute;
    top: 50%;
    left:50%;
    transform: translate(-50%,-50%);
    color: #fff;
}

</style>