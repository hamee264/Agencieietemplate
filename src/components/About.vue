<template>
  <div class="container">
    <div class="title">
        <div class="circle">p</div>
        <p>About</p>
    </div>
    <div class="text">
        <p>
        We started as a small group of passionate creators who believed that great ideas deserve bold execution. What began over coffee-fueled brainstorming sessions has grown into a thriving digital agency dedicated to helping brands stand out. 
    </p>
    <p>
        Our mission is simple: to craft creative, impactful solutions that drive results. With a vision to empower businesses to shine in a crowded world, we combine strategy, design, and a touch of magic to bring your ideas to life. Let’s make something amazing together!
    </p>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
    .container{
        padding: 60px 30px;
    }
    .title{
    text-align: left;
    display: flex;
    justify-content: space-between;
    /* border: #808080 solid 2px; */
    width: 90px;
    align-items: center;
    border-radius: 50px;
    padding-right: 5px;
    background: rgb(245, 247, 249);
 }
 .title .circle{
    height: 30px;
    width: 30px;
    border-radius: 50%;
    background: black;
    color: white;
    text-align: center;
 }
.text p{
    max-width: 800px;
    font-size: 25px;
    padding-top: 30px;
    line-height: 30px;
 }
</style>