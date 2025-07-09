<template>
  <div class="container">
    <!-- Sidebar with links -->
    <div class="aside-container">
      <a
        v-for="Service in Services"
        :key="Service.id"
        :href="'#' + Service.id"
        :class="{ active: activeId === Service.id }"
      >
        {{ Service.Title }}
      </a>
    </div>

    <!-- Main content -->
    <div class="main-container">
      <div
        class="loop-con"
        v-for="Service in Services"
        :key="Service.id"
        :id="Service.id"
        ref="sections"
      >
        <div class="each-services">
          <h2>{{ Service.Title }}</h2>
          <p class="description">{{ Service.Content }}</p>
          <div class="cont2">
            <div class="cont" v-for="cont in Service.Workers" :key="cont">
              <p>{{ cont }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeId: null, // track the current section in view
      Services: [
        {
          id: "web", // use ids for linking
          Title: "Web Design & Development",
          Content:
            "Your website is like your digital handshake—it’s the first thing people notice about you online. Our Web Design & Development services are all about making that handshake firm, friendly, and unforgettable.",
          Workers: [
            "UI UX Design",
            "Custom Website Design",
            "E-Commerce Development",
            "Content Management System (CMS)",
            "Website Maintenance and Support",
            "SEO Integration",
            "UX/UI Optimization",
          ],
        },
        {
          id: "digital",
          Title: "Digital Marketing",
          Content:
            "Let’s face it, the internet is a noisy place. But with our Digital Marketing services, you won’t just stand out—you’ll shine. Think of us as your online hype team.",
          Workers: [
            "SEO (Search Engine Optimization)",
            "PPC Advertising",
            "Social Media Marketing",
            "Email Marketing",
            "Influencer Campaigns",
          ],
        },
        {
          id: "branding",
          Title: "Branding & Creative Services",
          Content:
            "Your brand is more than a logo—it’s your story. Our branding brings your identity to life in a way that’s bold, beautiful, and 100% you.",
          Workers: [
            "Logo Design",
            "Brand Strategy",
            "Visual Identity",
            "Brand Guidelines",
            "Social Graphics",
            "Presentations",
            "Packaging Design",
          ],
        },
        {
          id: "app",
          Title: "App Design & Development",
          Content:
            "Got a brilliant app idea? Let’s make it a reality! Whether it’s a tool or a platform, we’ll build something sleek and smooth.",
          Workers: [
            "UI/UX Design",
            "Custom App Development",
            "Mobile Optimization",
            "App Store Optimization",
          ],
        },
      ],
    };
  },

  mounted() {
    window.addEventListener("scroll", this.onScroll);
  },

  beforeUnmount() {
    window.removeEventListener("scroll", this.onScroll);
  },

  methods: {
    onScroll() {
      const sections = this.$refs.sections;
      for (let section of sections) {
        const rect = section.getBoundingClientRect();
        if (rect.top <= 140 && rect.bottom >= 140) {
          this.activeId = section.id;
          break;
        }
      }
    },
  },
};
</script>

<style scoped>
html {
  scroll-behavior: smooth;
}

.container {
  display: flex;
  padding: 80px 40px;
  gap: 50px;
  align-items: flex-start;
  background: #fff;
}

/* Sidebar */
.aside-container {
  flex: 1;
  position: sticky;
  top: 120px;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.aside-container a {
  font-weight: 500;
  font-size: 17px;
  color: #555;
  text-decoration: none;
  transition: color 0.3s ease;
}

.aside-container a:hover {
  color: orangered;
}

.aside-container a.active {
  color: orangered;
  font-weight: 600;
  margin-left: 20px;
  transition: 0.5s all;
}

/* Main content */
.main-container {
  flex: 2;
  display: flex;
  flex-direction: column;
  gap: 60px;
}

.loop-con {
  border-bottom: 1px solid #020101;
  padding-bottom: 40px;
}

.each-services h2 {
  font-size: 28px;
  font-weight: 600;
  margin-bottom: 20px;
  color: #222;
}

.description {
  font-size: 16px;
  color: #666;
  max-width: 700px;
  line-height: 1.7;
  margin-bottom: 20px;
}

.cont2 {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.cont {
  border: #f4f4f4 1px solid;
  padding: 5px 10px;
  border-radius: 20px;
  font-size: 14px;
  color: black;
  font-weight: 500;
}

/* Responsive */
@media (max-width: 992px) {
  .container {
    flex-direction: column;
    padding: 50px 20px;
  }

  .aside-container {
    position: relative;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 15px;
    justify-content: center;
    padding-bottom: 30px;
    display: none;
  }
}
</style>
