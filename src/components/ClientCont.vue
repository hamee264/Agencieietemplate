<template>
  <div class="container">
    <div class="loop-con" v-for="comment in comments" :key="comment.id">
      <div class="cont">
        <h2>"</h2>
        <p>{{ comment.body }}</p>
      </div>

      <div class="img" v-if="comment.image">
        <img :src="comment.image" alt="" />
        <img :src="comment.image2" alt="" />
      </div>

      <div class="profile">
        <h3>{{ comment.name }}</h3>
        <p>{{ comment.company }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      comments: [
        {
          id: 1,
          body: "Working with this team felt like having a secret weapon. They took our scattered ideas and turned them into a website that screams 'wow!' Our customers can't stop raving about it.",
          image: "/src/assets/mar1.avif",
          image2: "/src/assets/mar2.avif",
          name: "Tobias Green",
          company: "Founder, GREENSPARK INNOVATIONS",
        },
        {
          id: 2,
          body: "Finally an agency that speaks our language! They understood our vision better than we did and brought it to life in a way that exceeded expectations. 10/10 would recommend!",
          image: "/src/assets/mar1.avif",
          image2: "/src/assets/mar2.avif",
          name: "Silas Leighton",
          company: "Managing Director, Venturevista",
        },
        {
          id: 3,
          body: "I came in with high hopes and they absolutely blew me away. From strategy to execution, every detail was on point. I'm telling everyone I know—hire them!",
          image: "/src/assets/mar1.avif",
          image2: "/src/assets/mar2.avif",
          name: "Orion Vance",
          company: "CEO, LUNAR LUX CO.",
        },
        {
          id: 4,
          body: "Our brand went from whisper to roar. The team's creativity and expertise made all the difference. We're getting noticed like never before!",
          image: "/src/assets/mar1.avif",
          image2: "/src/assets/mar2.avif",
          name: "Callum Yates",
          company: "Co-founder, Driftwood Media",
        },
        {
          id: 5,
          body: "Our online presence went from zero to hero in no time. The team made the process so seamless, I almost forgot I was working on a big project.",
          image: "/src/assets/mar1.avif",
          image2: "/src/assets/mar2.avif",
          name: "Jasper Lowell",
          company: "CEO, Copperleaf Enterprises",
        },
        {
          id: 6,
          body: "They made us feel like their most important client. The attention, quick responses, and innovative ideas were top-notch. We'll definitely be back for more!",
          image: "/src/assets/mar1.avif",
          image2: "/src/assets/mar2.avif",
          name: "Jasper Lowell",
          company: "Brand Manager, Stellar Bloom Studio",
        },
      ],
    };
  },
};
</script>

<style scoped>
.container {
  display: grid;
  grid-template-columns: 1fr; /* default for small screens */
  gap: 2rem;
  padding: 2rem;
}

@media (min-width: 600px) {
  .container {
    grid-template-columns: repeat(2, 1fr); /* tablets */
  }
}

@media (min-width: 992px) {
  .container {
    grid-template-columns: repeat(3, 1fr); /* large screens */
  }
}

.loop-con {
  
  display: flex;
  flex-direction: column;
  gap: 1rem;
  /* box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05); */
}

.cont {
  display: flex;
  flex-direction: row;
  gap: 20px;
  align-items: start;
  background: #f9f9f9;
  border-radius: 20px;
  padding: 1.5rem;
}

.cont h2 {
  font-size: 4rem;
  color: orangered;
  margin: 0;
}

.cont p {
  margin-top: 0.3rem;
  line-height: 1.6;
  font-size: 0.95rem;
}

.img {
  display: flex;
  gap: 0.5rem;
  margin-top: 1rem;
}

.img img {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  object-fit: cover;
  filter: grayscale(100%);

}

.profile h3 {
  margin: 0.5rem 0 0;
  font-size: 1.1rem;
}

.profile p {
  margin: 0;
  font-size: 0.9rem;
  color: #666;
}

@media (max-width: 450px) {
  .cont {
    flex-direction: column;
    gap: 10px;
  }

  .cont h2 {
    font-size: 2.5rem;
  }

  .cont p {
    font-size: 0.9rem;
  }
}
</style>
