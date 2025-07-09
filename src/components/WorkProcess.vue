<template>
  <section class="work-process">
    <div class="container">
      <!-- Top Intro Section -->
      <div class="Services">
        <div class="circle">p</div>
        <p>Our Work Process</p>
      </div>

      <div class="services-heading">
        <h1>From idea to impact—our process makes it easy, exciting, and effective!</h1>
      </div>
    </div>

    <!-- Cards Section -->
    <div class="cards-container">
      <div
        v-for="(step, index) in steps"
        :key="index"
        class="process-card"
        :class="{ active: activeIndex === index || isMobile }"
        @click="!isMobile && setActive(index)"
      >
        <!-- Always-visible number -->
        <div class="number">{{ index + 1 }}</div>

        <!-- Vertical title (desktop only) -->
        <div
          class="vertical-title"
          v-if="!isMobile && activeIndex !== index"
        >
          {{ step.title }}
        </div>

        <!-- Full content (shown on click or always on mobile) -->
        <transition name="fade" v-if="!isMobile">
          <div class="content" v-if="activeIndex === index">
            <h3>{{ step.title }}</h3>
            <p>{{ step.desc }}</p>
          </div>
        </transition>

        <div class="content" v-if="isMobile">
          <h3>{{ step.title }}</h3>
          <p>{{ step.desc }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      activeIndex: 0,
      isMobile: false,
      steps: [
        {
          title: "Discover & Strategize",
          desc: "We dive deep into understanding your brand, goals, and audience. Through collaborative discussions and research, we craft a clear roadmap tailored to your needs.",
        },
        {
          title: "Design & Develop",
          desc: "We create stunning visuals and craft intuitive user experiences. Every detail is designed to resonate with your brand and audience.",
        },
        {
          title: "Deploy & Launch",
          desc: "We launch with precision, ensuring everything works flawlessly across devices and platforms.",
        },
        {
          title: "Refine & Grow",
          desc: "We analyze performance, gather feedback, and fine-tune to ensure your brand stays competitive and thriving.",
        },
      ],
    };
  },
  mounted() {
    this.checkMobile();
    window.addEventListener("resize", this.checkMobile);
  },
  beforeUnmount() {
    window.removeEventListener("resize", this.checkMobile);
  },
  methods: {
    setActive(index) {
      this.activeIndex = index;
    },
    checkMobile() {
      this.isMobile = window.innerWidth <= 768;
    },
  },
};
</script>

<style scoped>
.work-process {
  padding: 80px 20px;
  max-width: 1400px;
  margin: auto;
}

/* Top Heading Section */
.container {
  padding: 50px 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.Services {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 200px;
  background: rgb(245, 247, 249);
  border-radius: 50px;
  padding: 5px 10px;
  margin-bottom: 15px;
}
.Services .circle {
  height: 30px;
  width: 30px;
  border-radius: 50%;
  background: black;
  color: white;
  text-align: center;
  line-height: 30px;
  font-weight: bold;
}
.services-heading h1 {
  font-size: 60px;
  font-weight: 500;
  letter-spacing: -2px;
  max-width: 850px;
  line-height: 72px;
  text-align: center;
}

/* Cards Layout */
.cards-container {
  display: flex;
  gap: 10px;
  overflow-x: auto;
  scroll-behavior: smooth;
  margin-top: 60px;
}

/* Individual Card */
.process-card {
  flex: 0 0 60px;
  height: 600px;
  background: #f2f2f2;
  border-radius: 30px;
  padding: 30px 20px;
  position: relative;
  cursor: pointer;
  transition: all 0.4s ease;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}
.process-card.active {
  flex: 1 1 auto;
  background: #0d0d0d;
  color: #fff;
  align-items: flex-start;
  text-align: left;
}

/* Number */
.number {
  font-size: 60px;
  font-weight: 700;
  color: orangered;
  margin-bottom: 20px;
  align-self: flex-start;
}
.process-card.active .number {
  color: white;
}

/* Title (vertical for desktop) */
.vertical-title {
  font-size: 12px;
  font-weight: 600;
  writing-mode: vertical-rl;
  transform: rotate(180deg);
  color: #222;
  flex-grow: 1;
  display: flex;
  align-items: center;
}

/* Content */
.content {
  margin-top: 40px;
}
.content h3 {
  font-size: 24px;
  font-weight: 600;
  margin-bottom: 15px;
}
.content p {
  font-size: 16px;
  line-height: 1.7;
  max-width: 500px;
}

/* Fade Animation */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.4s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

/* Responsive */
@media (max-width: 768px) {
  .cards-container {
    flex-direction: column;
    gap: 20px;
  }

  .process-card {
    position: static;
    flex: none !important;
    height: auto;
    padding: 20px;
    background: #0d0d0d;
    color: white;
    border-radius: 20px;
    align-items: flex-start;
    text-align: left;
    cursor: default;
    position: sticky;
  }

  .vertical-title {
    display: none;
  }

  .number {
    font-size: 32px;
    margin-bottom: 10px;
    color: white;
  }

  .content h3 {
    font-size: 20px;
  }

  .content p {
    font-size: 14px;
    line-height: 1.5;
  }

  .services-heading h1 {
    font-size: 35px;
    line-height: 48px;
    letter-spacing: -1px;
    max-width: 100%;
  }

  @media (max-width: 330px) {
    .services-heading h1 {
      font-size: 25px;
      line-height: 30px;
    }
  }
}
</style>
