<template>
  <div class="carousel-container">
    <!-- Navigation buttons in normal flow (flex row at top) -->
    <div class="carousel-header">
      <div class="carousel-nav">
        <button class="nav prev" @click="scrollLeft">&#8249;</button>
        <button class="nav next" @click="scrollRight">&#8250;</button>
      </div>
    </div>

    <!-- Scrollable carousel track -->
    <div class="carousel-track" ref="track">
      <div class="card" v-for="(card, index) in cards" :key="index">
        <p>{{ card.text }}</p>
        <img :src="card.image" alt="Illustration" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cards: [
        {
          text: "Get big agency results without breaking the bank.",
          image: "/src/assets/benefitcarbg.png",
        },
        {
          text: "Our team comes up with out-of-the-box ideas to make your brand stand out.",
          image: "/src/assets/benefitcar2bg.png",
        },
        {
          text: "We take care of generating leads while you focus on doing what you love—running your business!",
          image: "/src/assets/benefitcar3bg.png",
        },
        {
          text: "Your brand stays online 24/7 with our automated process.",
          image: "/src/assets/benefitcar4bg.png",
        },
        {
          text: "We understand your goals and help align your brand with measurable success.",
          image: "/src/assets/benefitcar5bg.png",
        },
        {
          text: "Designed to convert, built to impress — every project is backed by strategy.",
          image: "/src/assets/benefitcarbg.png",
        },
      ],
    };
  },
  methods: {
    scrollLeft() {
      this.$refs.track.scrollBy({ left: -320, behavior: "smooth" });
    },
    scrollRight() {
      this.$refs.track.scrollBy({ left: 320, behavior: "smooth" });
    },
  },
};
</script>

<style scoped>
.carousel-container {
  width: 100%;
  padding: 20px 30px;
}

/* Header area for nav buttons */
.carousel-header {
  display: flex;
  justify-content: flex-end;
  padding: 0 60px 20px;
}

.carousel-nav {
  display: flex;
  gap: 12px;
}

/* Nav button styling */
.nav {
  background: orangered;
  border: none;
  color: white;
  font-size: 40px;
  border-radius: 5px;
  cursor: pointer;
  padding: 0 20px;
}

/* Carousel track (scrollable row) */
.carousel-track {
  display: flex;
  overflow-x: auto;
  scroll-snap-type: x mandatory;
  scroll-behavior: smooth;
  gap: 30px;
  padding: 0 60px;

  /* 👇 Hide scrollbar across all major browsers */
  scrollbar-width: none; /* Firefox */
  -ms-overflow-style: none;  /* IE and Edge */
}
.carousel-track::-webkit-scrollbar {
  display: none; /* Chrome, Safari, Opera */
}

/* Card style */
.card {
  flex: 0 0 350px;
  /* background: white; */
  background: #f9f9f9;

  border-radius: 24px;
  padding: 30px 25px;
  scroll-snap-align: start;
  text-align: left;
  transition: transform 0.3s ease;
  justify-content: space-between;
  display: flex;
  flex-direction: column;
}
.card:hover {
  transform: translateY(-5px);
}

.card p {
  font-size: 24px;
  color: #333;
  font-weight: 500;
  line-height: 24px;
}

.card img {
  width: 100%;
  display: block;
  margin: 0;
  padding: 0;
  background: transparent; 
}

/* Responsive */
@media (max-width: 1024px) {
  .carousel-header {
    padding: 0 20px 15px;
  }

  .carousel-track {
    padding: 0 20px;
    gap: 20px;
  }

  .card {
    flex: 0 0 260px;
    padding: 20px;
  }

  .card p {
    font-size: 15px;
    line-height: 22px;
  }

  .nav {
    width: 32px;
    height: 32px;
    font-size: 18px;
  }
}

</style>
