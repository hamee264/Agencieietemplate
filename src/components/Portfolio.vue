<template>
  <div class="container">
     <div class="Portfolio">
        <div class="circle">p</div>
        <p>Our Portfolio</p>
    </div>
    <div class="Portfolio-heading">
        <h1>Explore the projects where we played, experimented, and built something amazing.</h1>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
    .container{
        padding: 50px 30px;
        display: flex;
        justify-content: center;
        flex-direction: column;
        justify-self: center;
        align-items: center;
    }
    .Portfolio{
    text-align: center;
    display: flex;
    justify-content: space-between;
    /* border: #808080 solid 2px; */
    width: 150px;
    align-items: center;
    border-radius: 50px;
    padding-right: 10px;
    background: rgb(245, 247, 249);
 }
 .Portfolio .circle{
    height: 30px;
    width: 30px;
    border-radius: 50%;
    background: black;
    color: white;
    text-align: center;
 }
 .Portfolio-heading h1 {
  font-size: 50px;
  font-weight: 500;
  letter-spacing: -3px;
  max-width: 850px;
  
  text-align: center;
}
@media (max-width: 768px) {
  .Portfolio-heading h1 {
    font-size: 35px;
    line-height: 48px;
    letter-spacing: -1px;
    max-width: 100%;
  }
}
@media (max-width:330px) {
  .Portfolio-heading h1{
    font-size: 25px;
    line-height: 30px;
  }

}
</style>