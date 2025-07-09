<template>
  <section class="faq-section">
    <div class="faq-wrapper">
      <!-- Left Column -->
      <div class="faq-left">
        <div class="faq-header">
          <p class="faq-subtitle">Frequently Asked Questions</p>
          <h2 class="faq-title">
            FAQ It Up! Your curiosity<br />
            meets our expertise —<br />
            let’s clear things up!
          </h2>
          <p class="faq-description">
            We’ve gathered all the important info right here. Explore our FAQs
            and find the answers you need.
          </p>
        </div>
      </div>

      <!-- Right Column -->
      <div class="faq-right">
        <div class="faq-item" v-for="(faq, index) in Faqs" :key="faq.question">
          <!-- QUESTION SECTION -->
          <div class="faq-question-box" @click="toggle(index)">
            <div class="faq-question-text">
              <h3>{{ faq.question }}</h3>
            </div>
            <div class="faq-icon-box">
              <i
                :class="[
                  'fas',
                  'fa-chevron-down',
                  'faq-icon',
                  { rotate: activeIndex === index },
                ]"
              ></i>
            </div>
          </div>

          <!-- ANSWER SECTION -->
          <transition name="faq">
            <div class="faq-answer-box" v-show="activeIndex === index">
              <div class="faq-answer-text">
                <p>{{ faq.answer }}</p>
              </div>
              <div class="faq-answer-image">
                <img src="/src/assets/mar2.avif" alt="" />
              </div>
            </div>
          </transition>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  data() {
    return {
      activeIndex: null,
      Faqs: [
        {
          question: "What services do you offer?",
          answer:
            "We offer web design, branding, strategy, SEO, and digital marketing.",
        },
        {
          question: "How long does it take to design a website?",
          answer:
            "Typically 2–6 weeks depending on complexity and feedback loops.",
        },
        {
          question: "Do you work with small businesses or just big brands?",
          answer:
            "We collaborate with both. Every great brand starts somewhere.",
        },
        {
          question: "Can I customize the packages?",
          answer: "Absolutely! We tailor our services to your needs.",
        },
        {
          question: "How do you measure the success of a marketing campaign?",
          answer:
            "We use KPIs like ROI, engagement, conversion rate, and customer feedback.",
        },
        {
          question: "What makes your agency different?",
          answer:
            "We fuse creativity with strategy, ensuring each project is both beautiful and effective.",
        },
        {
          question: "What’s your creative process like?",
          answer:
            "We begin with research, define goals, iterate designs, and deliver with precision.",
        },
        {
          question: "Do you offer post-launch support?",
          answer:
            "Yes, we offer maintenance, updates, and analytics to ensure continued success.",
        },
      ],
    };
  },
  methods: {
    toggle(index) {
      this.activeIndex = this.activeIndex === index ? null : index;
    },
  },
};
</script>
<style scoped>
/* @import "@fortawesome/fontawesome-free/css/all.min.css"; */

.faq-section {
  padding: 100px 20px;
  background: #fff;
}

.faq-wrapper {
  display: flex;
  max-width: 1200px;
  margin: 0 auto;
  gap: 60px;
}

.faq-left {
  flex: 1;
  min-width: 250px;
}

.faq-header {
  position: sticky;
  top: 100px;
  background: #fff;
}

.faq-subtitle {
  font-size: 0.9rem;
  color: #aaa;
  text-transform: uppercase;
  margin-bottom: 10px;
}

.faq-title {
  font-size: 2.5rem;
  font-weight: 800;
  line-height: 1.3;
  margin-bottom: 15px;
  color: #111;
}

.faq-description {
  font-size: 1rem;
  color: #666;
  max-width: 500px;
}

/* Right Side */
.faq-right {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 20px;
  /* padding: 10px; */
}

/* Entire FAQ item */
.faq-item {
  /* border: 1px solid #eee; */
  padding: 20px 10px;
  gap: 10px;
  border-radius: 20px;
  background: #f7f7f7;
}

/* Question section */
.faq-question-box {
  display: flex;
  justify-content: space-between;
  align-items: center;
  cursor: pointer;
  padding: 14px 20px;
  border-radius: 12px;
  /* transition: border 0.3s ease, background 0.3s ease; */
  /* border: 1px solid transparent; */
}

/* .faq-question-box:hover {
  border: 1px solid #ddd;
  background: #fafafa;
} */

.faq-question-text h3 {
  margin: 0;
  font-size: 1rem;
  font-weight: 600;
  color: #333;
}

.faq-icon-box {
  transition: transform 0.3s;
  /* background: white; */
padding: 5px 10px;


}
.faq-icon-box:hover{
  border-radius: 6px;
background: orangered;
}
.faq-icon-box:hover .faq-icon{

color: white;

}

.faq-icon {
  font-size: 1rem;
  color: #666;
  transition: transform 0.3s ease;
}

.rotate {
  transform: rotate(180deg);
}

/* Answer section */
.faq-answer-box {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 16px 20px;
  align-items: center;
  background: white;
  border-radius: 20px;
  /* gap: 20px; */
}
img {
  width: 100%;
}

.faq-answer-text {
  flex: 2;
  font-size: 0.95rem;
  color: #555;
  line-height: 1.6;
}

.faq-answer-image {
  flex: 1;
  max-width: 100px;
  background: #f5f5f5;
  border-radius: 10px;
  height: 80px;
  display: none;
}

/* Transition animation */
.faq-enter-active,
.faq-leave-active {
  transition: all 0.3s ease;
}

.faq-enter-from,
.faq-leave-to {
  max-height: 0;
  opacity: 0;
  overflow: hidden;
}

.faq-enter-to,
.faq-leave-from {
  max-height: 500px;
  opacity: 1;
}

@media (max-width: 768px) {
  .faq-wrapper {
    flex-direction: column;
  }

  .faq-header {
    position: static;
  }

  .faq-answer-box {
    flex-direction: column;
  }
}
</style>
