<template>
  <div class="container">
    <div class="benefits">
        <div class="circle">p</div>
        <p>Benefits</p>
    </div>
    <h3>See why partnering with us is the smartest move.</h3>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.container{
    padding: 30px 30px;
    text-align: left;
}
 .benefits{
    text-align: left;
    display: flex;
    justify-content: space-between;
    /* border: #808080 solid 2px; */
    width: 110px;
    align-items: center;
    border-radius: 50px;
    padding-right: 5px;
    background: rgb(245, 247, 249);
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
     font-size: 65px;
  font-weight: 500;
  letter-spacing: -3px;
  max-width: 750px;
  line-height: 72px;
  text-align: left;
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