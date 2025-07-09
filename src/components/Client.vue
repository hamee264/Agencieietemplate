<template>
  <div class="container">
    <div class="benefits">
      <div class="circle">p</div>
      <p>Client Stories</p>
    </div>
    <h3>Hear stories straight from the people we helped!</h3>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.container {
 padding: 30px 30px;
        display: flex;
        justify-content: center;
        flex-direction: column;
        justify-self: center;
        align-items: center;
}
.benefits {
  text-align: left;
  display: flex;
  justify-content: space-between;

  width: 150px;
  align-items: center;
  border-radius: 50px;
  padding-right: 5px;
  background: rgb(245, 247, 249);
}
.benefits .circle {
  height: 30px;
  width: 30px;
  border-radius: 50%;
  background: black;
  color: white;
  text-align: center;
}
.img img {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  border: 2px solid white;
  box-shadow: 0 0 0 1px #ccc;
  margin-left: -10px;
  background: #eee;
  filter: grayscale(100%);


}
h3 {
   font-size: 50px;
  font-weight: 500;
  letter-spacing: -3px;
  max-width: 800px;
  
  text-align: center;
}
@media (max-width: 768px) {
  h3 {
    font-size: 35px;
    line-height: 48px;
    letter-spacing: -1px;
    text-align: center;
  }
}
@media (max-width: 330px) {
  h3 {
    font-size: 25px;
    line-height: 30px;
  }
}
</style>