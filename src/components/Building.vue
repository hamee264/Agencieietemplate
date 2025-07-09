<template>
  <div class="container">
    <div class="top-con">
      <h1>
        <span>Building</span> brands, <span>boosting</span> businesses, and
        <span>redefining</span> possibilities. Let’s grow your brand together.
      </h1>
    </div>
    <div class="loop-con">
      <div class="loop" v-for="item in items" :key="item.id">
        <div class="dotted-con">
          <h1>{{ item.num }}</h1>
          <p>{{ item.pa }}</p>
        </div>
        <p>{{ item.body }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          id: 1,
          num: "250+",
          pa: "Projects Delivered",
          body: "We’ve successfully completed over 250 projects—and we’re just getting started!",
        },
        {
          id: 2,
          num: "70%",
          pa: "Business Growth",
          body: "Our strategies have helped clients achieve up to 70% revenue growth in just one year!",
        },
        {
          id: 3,
          num: "500+",
          pa: "Happy Clients",
          body: "More than 500 satisfied clients trust us to bring their ideas to life.",
        },
      ],
    };
  },
};
</script>

<style scoped>
.top-con {
  max-width: 800px;
  margin: auto;
}

.top-con h1 {
  font-size: 50px;
  font-weight: 500;
  letter-spacing: -2px;
  line-height: 60px;
  text-align: center;
}

.top-con h1 span {
  color: orangered;
}

.loop-con {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
  padding: 50px 30px;
  justify-items: center;
  place-items: center;
}

.loop {
  width: 100%;
  max-width: 350px;
  background: #fff;
  border-radius: 12px;
  padding: 10px;
  /* box-shadow: 0 4px 20px rgba(0, 0, 0, 0.03); */
}

.dotted-con {
  border: 1px dashed black;
  border-radius: 20px;
  padding: 20px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.dotted-con h1 {
  font-size: 60px;
  font-weight: 600;
  margin: 0;
  line-height: 1;
  color: orangered;
}

.dotted-con p {
  font-size: 18px;
  margin: 5px 0 0 0;
  color: black;
}

.loop p {
  font-size: 14px;
  color: grey;
  padding: 10px 0 0 0;
}

/* Responsive styles for tablets and mobile */
@media (max-width: 768px) {
  .top-con {
    max-width: 100%;
    padding: 0 20px;
  }

  .top-con h1 {
    font-size: 35px;
    line-height: 48px;
    letter-spacing: -1px;
    text-align: center;
  }

  .loop-con {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 30px 20px;
    gap: 20px;
  }

  .loop {
    max-width: 100%;
    width: 100%;
  }

  .dotted-con {
    align-items: center;
    text-align: center;
  }

  .dotted-con p,
  .loop p {
    text-align: center;
  }
}
@media (max-width:330px) {
  .top-con h1{
    font-size: 25px;
    line-height: 30px;
  }

}
</style>