<template>
  <header>
    <div class="logo">
      <img src="/src/assets/navlogo.png" alt="Logo" />
    </div>

    <nav :class="{ open: isMenuOpen }">
      <a href="#services" @click="handleLinkClick">Services</a>
      <a href="#projects" @click="handleLinkClick">Project</a>
      <a href="#process" @click="handleLinkClick">Process</a>
      <a href="#reviews" @click="handleLinkClick">Reviews</a>
      <a href="#pricing" @click="handleLinkClick">Pricing</a>
    </nav>

    <div class="contact">
      <p>Contact Me</p>
    </div>

    <div class="menubtn" @click="toggleMenu">
      <span></span>
      <span></span>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      isMenuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    handleLinkClick() {
      this.isMenuOpen = false;
    },
  },
  mounted() {
    // Enable smooth scroll
    document.documentElement.style.scrollBehavior = "smooth";
  },
};
</script>

<style scoped>
html {
  scroll-behavior: smooth;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: white;
  padding: 20px 30px;
  z-index: 999;
  position: relative;
}

.logo img {
  width: 120px;
}

nav {
  display: flex;
  align-items: center;
  gap: 20px;
  transition: all 0.3s ease-in-out;
}

nav a {
  display: flex;
  position: relative;
  align-items: center;
  font-weight: 500;
  font-size: 1rem;
  color: black;
  text-decoration: none;
}

nav a::after {
  content: "";
  width: 0;
  position: absolute;
  height: 2px;
  background: orangered;
  top: 100%;
  left: 0;
  transition: 0.4s ease;
}

nav a:hover::after {
  width: 100%;
}

.contact p {
  background: black;
  padding: 7px 14px;
  border-radius: 10px;
  font-size: 1rem;
  color: white;
  cursor: pointer;
  transition: 0.3s;
}

.contact p:hover {
  opacity: 0.7;
}

.menubtn {
  border: orangered solid 2px;
  width: 35px;
  display: none;
  flex-direction: column;
  gap: 4px;
  padding: 4px;
  border-radius: 6px;
  cursor: pointer;
}

.menubtn span {
  height: 2px;
  background: black;
  width: 100%;
}

/* Responsive Styles */
@media (max-width: 768px) {
  nav {
    position: absolute;
    top: 100%;
    left: 0;
    width: 100%;
    flex-direction: column;
    gap: 20px;
    padding: 25px 30px;
    display: none;
    background: #ffffff;
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
    border-bottom: 1px solid #eee;
    z-index: 1000;
    transition: all 0.3s ease-in-out;
  }

  nav.open {
    display: flex;
  }

  nav a {
    font-size: 1.1rem;
    padding: 10px 0;
    width: 100%;
    border-bottom: 1px solid #f0f0f0;
    text-align: left;
  }

  .contact {
    display: none;
  }

  .menubtn {
    display: flex;
    padding: 6px 8px;
    border-radius: 8px;
    gap: 6px;
    width: 40px;
  }

  .menubtn span {
    height: 3px;
    background: black;
    width: 100%;
    border-radius: 2px;
  }
}

@media (max-width: 480px) {
  nav a {
    font-size: 1rem;
  }

  .logo img {
    width: 100px;
  }

  header {
    padding: 15px 20px;
  }
}
</style>
