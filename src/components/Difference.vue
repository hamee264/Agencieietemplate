<template>
  <div class="container">
     <div class="Difference">
        <div class="circle">p</div>
        <p>Our Difference</p>
    </div>
    <div class="Difference-heading">
        <h1>While others copy and paste, we innovate and elevate. Your brand gets the VIP treatment it truly deserves.</h1>
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
    .Difference{
    text-align: center;
    display: flex;
    justify-content: space-between;
    /* border: #808080 solid 2px; */
    width: 170px;
    align-items: center;
    border-radius: 50px;
    padding-right: 10px;
    background: rgb(245, 247, 249);
 }
 .Difference .circle{
    height: 30px;
    width: 30px;
    border-radius: 50%;
    background: black;
    color: white;
    text-align: center;
 }
 .Difference-heading h1 {
   font-size: 50px;
  font-weight: 500;
  letter-spacing: -3px;
  max-width: 850px;
  
  text-align: center;
}
@media (max-width: 768px) {
  .Difference-heading h1 {
    font-size: 35px;
    line-height: 48px;
    letter-spacing: -1px;
    max-width: 100%;
  }
}
@media (max-width:330px) {
  .Difference-heading h1{
    font-size: 25px;
    line-height: 30px;
  }

}
</style>