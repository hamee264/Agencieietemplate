<template>
  <div class="container">
    <div class="benefits">
        <div class="circle">p</div>
        <p>Pricing Plans</p>
    </div>
    <h3>Affordable, transparent pricing tailored to your business—because every detail matters!</h3>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.container{
    padding: 30px 30px;
    text-align: center;
    justify-self: center;
}
 .benefits{
    text-align: center;
    display: flex;
    justify-content: space-between;
    /* border: #808080 solid 2px; */
    width: 150px;
    align-items: center;
    border-radius: 50px;
    padding-right: 5px;
    background: rgb(245, 247, 249);
    justify-self: center;
 }
 .benefits .circle{
    height: 30px;
    width: 30px;
    border-radius: 50%;
    background: black;
    color: white;
    text-align: center;
 }
 h3{
     font-size: 50px;
  font-weight: 500;
  letter-spacing: -3px;
  line-height: 50px;
  /* text-align: left; */
  max-width: 750px;

 }
@media (max-width: 768px) {
  h3 {
   font-size: 35px;
    line-height: 48px;
    letter-spacing: -1px;
    text-align: center;
  }
 }
 @media (max-width:330px) {
   h3{
    font-size: 25px;
    line-height: 30px;
  }

}
</style>