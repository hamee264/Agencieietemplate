<template>
  <div class="container">
    <section class="comparison-section">
      <!-- Others Heading -->
      <div class="column-wrapper">
        <h2 class="heading others-heading">Others</h2>
        <div class="column others">
          <ul>
            <li v-for="(item, index) in othersList" :key="index">
              <span class="emoji">😞</span>
              {{ item }}
            </li>
          </ul>
        </div>
      </div>

      <!-- Agent-G Heading -->
      <!-- Agent-G Heading -->
      <div class="column-wrapper">
        <h2 class="heading agent-heading">
          <img src="../assets/quoteimg7.svg" alt="Agent-G Logo" class="logo" />
          Agent-G
        </h2>
        <div class="column agent-g">
          <ul>
            <li v-for="(item, index) in agentGList" :key="index">
              <span class="icon">
                <i :class="['fa-solid', item.icon]"></i>
              </span>
              {{ item.text }}
            </li>
          </ul>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      othersList: [
        "Generic Solutions",
        "Jargon Overload",
        "Boring Creativity",
        "Fluff Metrics",
        "One-Time Campaigners",
        "Hidden Costs",
        "Outdated Methods",
        "Limited Scope",
        "Reactive Tactics",
        "Just Another Client",
      ],
      agentGList: [
        { icon: "fa-leaf", text: "Personalized Plans" },
        { icon: "fa-magnifying-glass", text: "Plain Talk" },
        { icon: "fa-rocket", text: "Bold Ideas" },
        { icon: "fa-chart-bar", text: "Real ROI" },
        { icon: "fa-handshake", text: "Long-Term Partners" },
        { icon: "fa-tags", text: "Transparent Pricing" },
        { icon: "fa-bolt", text: "Innovative Tools" },
        { icon: "fa-briefcase", text: "Full-Service Experts" },
        { icon: "fa-crown", text: "Proactive Strategies" },
        { icon: "fa-heart", text: "Passion & Care" },
      ],
    };
  },
};
</script>

<style scoped>
.container {
  padding: 30px;
}

.comparison-section {
  display: flex;
  flex-direction: row;
  max-width: 900px;
  width: 100%;
  margin: auto;
  border-radius: 16px;
  overflow: hidden;
  /* box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1); */
}

/* Wrap each column and heading */
.column-wrapper {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: stretch;
}

/* Column box */
.column {
  padding: 2rem;
  height: 100%;
}

/* Rounded corners only on outside */
.others {
  background-color: #f8f9fa;
  border-top-left-radius: 16px;
  border-bottom-left-radius: 16px;
}

.agent-g {
  background-color: #0a0a0a;
  color: #fff;
  border-top-right-radius: 16px;
  border-bottom-right-radius: 16px;
}

/* Headings */
.heading {
  font-size: 1.8rem;
  margin-bottom: 1rem;
  margin-left: 1rem;
  display: flex;
  align-items: center;
}

.logo {
  height: 24px;
  margin-right: 0.5rem;
}

/* List Styles */
ul {
  list-style: none;
  padding: 0;
}

li {
  display: flex;
  align-items: center;
  margin-bottom: 1rem;
  font-size: 1.1rem;
}

.emoji,
.icon {
  margin-right: 0.75rem;
  font-size: 1.3rem;
}

/* Responsive */
@media (max-width: 768px) {
  .comparison-section {
    flex-direction: column;
    border-radius: 0;
    overflow: visible;
    box-shadow: none;
  }

  .others,
  .agent-g {
    border-radius: 16px;
    margin-bottom: 1.5rem;
  }

  .heading {
    margin-left: 0;
    text-align: center;
  }
}

</style>
