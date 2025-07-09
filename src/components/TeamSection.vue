<template>
  <section class="team-section">
    <div class="team-grid">
      <div
        v-for="(member, index) in teamMembers"
        :key="index"
        class="team-card"
        :class="{ 'highlight': member.highlight }"
      >
        <div v-if="member.label" class="label">{{ member.label }}</div>

        <img :src="member.image" alt="Team Member" class="member-photo" />

        <h3 class="member-name">{{ member.name }}</h3>
        <p class="member-role">{{ member.role }}</p>

        <div class="social-links">
          <a v-if="member.linkedin" :href="member.linkedin" target="_blank">
            <i class="fab fa-linkedin"></i>
          </a>
          <a v-if="member.x" :href="member.x" target="_blank">
            <i class="fab fa-x-twitter"></i>
          </a>
        </div>
      </div>

      <!-- Join Us Card -->
      <div class="team-card join-card">
        <h3>You can be here</h3>
        <p>
          We value curiosity, collaboration, and a can-do attitude. <br />
          Come join a team that celebrates your unique skills.
        </p>
        <a href="#" class="join-btn">Join Our Team</a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      teamMembers: [
        {
          name: "Zephyr Callahan",
          role: "Lead Designer / Brand Strategist",
          image: "/src/assets/mar1.avif",
          label: "CREATIVE WIZARD",
          linkedin: "#",
          x: "#",
        },
        {
          name: "Thane Vesper",
          role: "Business Development Manager",
          image: "/src/assets/mar1.avif",
          label: "STRATEGY GENIUS",
          linkedin: "#",
          x: "#",
        },
        {
          name: "Leander Frost",
          role: "Lead Developer",
          image: "/src/assets/mar1.avif",
          label: "TECH ALCHEMIST",
          linkedin: "#",
          x: "#",
        },
      ],
    };
  },
};
</script>

<style scoped>
.team-section {
  padding: 60px 20px;
}

.team-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}

.team-card {
  background: #f7f7f7;
  border-radius: 16px;
  padding: 10px;
  max-width: 300px;
  text-align: left;
  width: 100%;
  /* box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08); */
  position: relative;
}

.label {
  position: absolute;
  top: -10px;
  left: 10px;
  background: #ff4500;
  color: white;
  padding: 4px 10px;
  font-size: 0.75rem;
  font-weight: bold;
  border-radius: 6px;
}

.member-photo {
  width: 100%;
  object-fit: cover;
  border-radius: 12px;
  margin-bottom: 10px;
}

.member-name {
  font-size: 1.5rem;
  font-weight: bold;
  margin-bottom: 4px;
}

.member-role {
  color: #666;
  font-size: 0.95rem;
  margin-bottom: 12px;
}

.social-links a {
  margin: 0 5px;
  font-size: 1.1rem;
  color: #111;
}

.join-card {
  background: #ff4f24;
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.join-card h3 {
  font-size: 1.4rem;
  margin-bottom: 10px;
}

.join-card p {
  font-size: 0.95rem;
  margin-bottom: 20px;
}

.join-btn {
  background: white;
  color: #ff4f24;
  padding: 10px 16px;
  border-radius: 6px;
  font-weight: bold;
  text-decoration: none;
  display: inline-block;
  margin-top: auto;
}

.join-btn:hover {
  background: #ffe7e2;
}

/* ✅ Responsive for iPad and below */
@media (max-width: 1024px) {
  .team-grid {
    flex-direction: column;
    align-items: center;
  }

  .team-card {
    max-width: 100%;
    width: 100%;
  }
}
</style>
