<template>
  <section class="portfolio-section">
    <div
      class="portfolio-card"
      v-for="(project, index) in projects"
      :key="index"
    >
      <!-- Image -->
      <div class="main-image-wrapper">
        <img :src="project.image" :alt="project.title" class="main-image" />
      </div>

      <!-- Tags and Details -->
      <div class="case-details">
        <div class="tags">
          <span v-for="(tag, i) in project.tags" :key="i" class="tag">
            {{ tag }}
          </span>
        </div>

        <h2 class="case-title">{{ project.title }}</h2>

        <a href="#" class="view-button">
          <span>View Case Study</span>
          <span class="arrow">›</span>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          title: "CritterShield – Pest Solutions Rebranding",
          image: "/src/assets/mar2.avif",
          tags: [
            "DISCOVERY & RESEARCH",
            "WEBSITE DESIGN",
            "CONTENT STRATEGY",
            "SEO & MARKETING INTEGRATION",
            "RE BRANDING",
          ],
        },
        {
          title: "GlowSpa – Wellness Site Makeover",
          image: "/src/assets/mar2.avif",
          tags: [
            "UI DESIGN",
            "BRAND REFRESH",
            "DEVELOPMENT",
            "STRATEGY",
          ],
        },
        {
          title: "TechTalk – Community Blog Platform",
          image: "/src/assets/mar2.avif",
          tags: [
            "BLOG DEVELOPMENT",
            "COMMUNITY STRATEGY",
            "DARK MODE DESIGN",
          ],
        },
      ],
    };
  },
};
</script>

<style scoped>
/* Outer container for all cards */
.portfolio-section {
  padding: 60px 20px;
  display: flex;
  flex-direction: column;
  gap: 40px;
  align-items: center;
}

/* Single Card Container */
.portfolio-card {
  width: 100%;
  max-width: 900px;
  /* background: #f6f6f6; */
  /* background: linear-gradient(to bottom, #fff, #f9f9f9); */
  border-radius: 30px;
  /* box-shadow: 0 10px 20px rgba(0, 0, 0, 0.05); */
  padding: 40px 20px;
  overflow: hidden;
}

/* Image Styling */
.main-image-wrapper {
  overflow: hidden;
  border-radius: 16px;
  margin-bottom: 30px;
}
.main-image {
  width: 100%;
  object-fit: cover;
  display: block;
  border-radius: 16px;
}

/* Tags */
.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-bottom: 18px;
}
.tag {
  border: #eee 2px solid;
  padding: 6px 12px;
  font-size: 13px;
  border-radius: 999px;
  font-weight: 500;
  color: #333;
}

/* Title */
.case-title {
  font-size: 24px;
  font-weight: 600;
  margin-bottom: 20px;
  color: #111;
}

/* Button */
.view-button {
  display: inline-flex;
  align-items: center;
  background: #000;
  color: #fff;
  padding: 14px 24px;
  border-radius: 30px;
  font-weight: 600;
  text-decoration: none;
  transition: background 0.3s ease;
  width: 100%;
  justify-content: space-between;
}
.view-button:hover {
  background: orangered;
}
.arrow {
  font-size: 18px;
}
</style>
