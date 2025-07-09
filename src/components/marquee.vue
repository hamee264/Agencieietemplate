<template>
  <div class="marquee-wrapper">
    <div class="marquee">
      <div class="track">
        <span v-for="(word, index) in repeatedWords" :key="index" class="marquee-item">
          {{ word }}
          <img class="dot" src="/src/assets/mar1.avif" alt="dot" />
        </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      words: [
        "I can’t stop recommending them",
        "A total game-changer for us",
        "They are like digital magicians",
        "These Folks get it",
        "Best Decision we ever made",
      ],
    };
  },
  computed: {
    repeatedWords() {
      return [...this.words, ...this.words, ...this.words]; // Repeat for smooth loop
    },
  },
};
</script>

<style scoped>
.marquee-wrapper {
  overflow: hidden;
  /* background: #000; */
  padding: 30px 0;
  /* color: white; */
  mask-image: linear-gradient(to right, rgba(0, 0, 0, 0) 0%, rgb(0, 0, 0) 12.5%, rgb(0, 0, 0) 87.5%, rgba(0, 0, 0, 0) 100%);
}

.marquee {
  display: flex;
  align-items: center;
}

.track {
  display: inline-flex;
  animation: scroll 40s linear infinite;
  font-size: 18px;
  font-weight: 500;
  white-space: nowrap;
  align-items: center;
  color: black;
}

.marquee-item {
  display: flex;
  align-items: center;
  margin-right: 50px;
}

.track img.dot {
  width: 60px;
  height: 60px;
  border-radius: 20px;
  margin-left: 20px;
  object-fit: cover;
}


@keyframes scroll {
  0% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(-50%);
  }
}


@media (max-width: 768px) {
  .track {
    font-size: 16px;
  }

  .track img.dot {
    width: 30px;
    height: 30px;
    margin-left: 15px;
  }

  .marquee-item {
    margin-right: 30px;
  }
}
</style>
