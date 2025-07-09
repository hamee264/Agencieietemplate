<template>
  <div class="container">
    <h1>We don’t just work together—we <span>grow</span> together.</h1>
    <div class="img-con">
      <img src="/src/assets/quoteimg.svg" alt="" />
      <img src="/src/assets/quoteimg2.svg" alt="" />
      <img src="/src/assets/quoteimg3.svg" alt="" />
      <img src="/src/assets/quoteimg4.svg" alt="" />
      <img src="/src/assets/quoteimg5.svg" alt="" />
      <img src="/src/assets/quoteimg6.svg" alt="" />
      <img src="/src/assets/quoteimg7.svg" alt="" />
      <img src="/src/assets/quoteimg8.svg" alt="" />
      <img src="/src/assets/quoteimg9.svg" alt="" />
      <img src="/src/assets/quoteimg10.svg" alt="" />
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.container {
  padding: 50px 30px;
  text-align: center;
}
.container h1 {
  font-size: 55px;
  font-weight: 500;
  letter-spacing: -3px;
  line-height: 72px;
  max-width: 750px;
  margin: auto;
}
.container h1 span {
  color: orangered;
}

.img-con {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 16px;
  margin-top: 50px;
  justify-content: center;
  max-width: 1000px;
  margin-left: auto;
  margin-right: auto;
}

.img-con img {
  width: 100%;
  background: #f4f4f4;
  padding: 20px;
  border-radius: 16px;
  height: 100px;
  object-fit: contain;
  /* transition: transform 0.3s ease, box-shadow 0.3s ease; */
}

.img-con img:hover {
  transform: translateY(-4px);
  /* box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1); */
}

@media (max-width: 1024px) {
  .img-con {
    grid-template-columns: repeat(4, 1fr);
  }
}

@media (max-width: 768px) {
  .container h1 {
    font-size: 35px;
    line-height: 48px;
    letter-spacing: -1px;
  }
  .img-con {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media (max-width: 480px) {
  .img-con {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 330px) {
  .container h1 {
    font-size: 25px;
    line-height: 30px;
  }
}

</style>