<template>
  <div class="container">
    <h1>
        Big ideas, smart strategies, and endless creativity to supercharge⚡your brand!
    </h1>
    <p  class="intro-text">
        Your go-to agency for designs that inspire and strategies that deliver. We turn ideas into lasting impressions.
    </p>
    <p class="contact">Contact Me</p>
    <div class="star-icon">
        <div class="stars">
            <i class="fas fa-star"></i> 
            <i class="fas fa-star"></i> 
            <i class="fas fa-star"></i> 
            <i class="fas fa-star"></i> 
            <i class="fas fa-star"></i> 
        </div>
        <p>Over 200+ Five Star Reviews</p>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
    .container {
  text-align: left;
  padding: 50px 60px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.container h1 {
  font-size: 60px;
  font-weight: 500;
  letter-spacing: -3px;
  max-width: 800px;
  line-height: 72px;
}

.container .intro-text {
  font-size: 18px;
  font-weight: 500;
  padding: 30px 0 20px 0;
  line-height: 26px;
  max-width: 500px;
  color: grey;
}

.contact {
  /* border: orangered solid 1px; */
  background: black;
  padding: 10px 15px;
  border-radius: 10px;
  font-size: 15px;
  color: white;
  width: fit-content;
  text-align: center;
  cursor: pointer;
  margin-top: 10px;
}

.star-icon {
  margin: 30px 0px;
  display: flex;
  align-items: center;
  gap: 15px;
  flex-wrap: wrap;
}

.star-icon i {
  color: orangered;
  font-size: 16px;
}

.star-icon p {
  font-size: 15px;
  font-weight: 400;
  color: #333;
}

/* ✅ Responsive Styles */
@media (max-width: 768px) {
  .container {
    text-align: center;
    align-items: center;
    padding: 40px 20px;
  }

  .container h1 {
    font-size: 35px;
    line-height: 48px;
    letter-spacing: -1px;
    max-width: 100%;
  }

  .container .intro-text {
    font-size: 16px;
    line-height: 24px;
    padding: 20px 0;
    max-width: 100%;
  }

  .contact {
    font-size: 14px;
    padding: 10px 20px;
  }

  .star-icon {
    flex-direction: column;
    align-items: center;
    gap: 10px;
  }

  .star-icon i {
    font-size: 14px;
  }
}
@media (max-width:330px) {
  .container h1{
    font-size: 25px;
    line-height: 30px;
  }

}
</style>