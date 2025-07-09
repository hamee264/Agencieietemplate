<template>
  <div class="container">
    <div class="pricing-container">
      <div class="column">
        <div class="pricing-card-wrapper">
          <div v-for="(plan, index) in Plans" :key="index" class="pricing-card">
            <!-- Left: Features -->
            <div class="left-cont">
              <ul>
                <li v-for="feature in plan.features" :key="feature">
                  ✔ {{ feature }}
                </li>
              </ul>
            </div>

            <!-- Right: Plan Info -->
            <div class="right-cont">
              <div class="title">
                <div class="circle">P</div>
                <p class="plan-title">{{ plan.title }}</p>
              </div>

              <div class="price">
                <!-- Show toggle buttons ONLY for the first card -->
                <div v-if="index === 0" class="period">
                  <button
                    :class="{ active: selectedBilling === 'monthly' }"
                    @click="selectedBilling = 'monthly'"
                  >
                    Monthly
                  </button>
                  <button
                    :class="{ active: selectedBilling === 'yearly' }"
                    @click="selectedBilling = 'yearly'"
                  >
                    Yearly
                  </button>
                </div>

                <div class="sup-cont">
                  <div class="start">
                    <p v-if="plan.start" class="start-text">{{ plan.start }}</p>
                    <div class="current-cont">
                      <h2 class="current-price">
                        {{
                          index === 0
                            ? selectedBilling === "yearly"
                              ? plan.yearlyPrice || plan.price
                              : plan.price
                            : plan.price
                        }}
                      </h2>
                      <p class="price-time">{{ plan.time }}</p>
                    </div>
                  </div>
                </div>

                <p class="discount" v-if="plan.discountNote">
                  {{ plan.discountNote }}
                </p>
              </div>

              <p class="target">{{ plan.target }}</p>
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
      selectedBilling: "monthly",
      Plans: [
        {
          title: "Marketing Momentum",
          price: "$209",
          yearlyPrice: "$2,099",
          time: "/month",
          originalPrice: "$299",
          discountNote: "save ~30% if paid yearly",
          month: "Monthly",
          year: "Yearly",
          features: [
            "Social Media Management (3 platforms, 12 posts/month)",
            "Monthly Email Campaigns (up to 3)",
            "Blog Content (2 articles/month)",
            "Basic Analytics Reports",
            "Post Scheduling & Optimization",
            "Quarterly Competitor Analysis",
            "Engagement Monitoring & Response",
          ],
          target:
            "Small to mid-sized businesses building a strong, consistent online presence",
        },
        {
          title: "Brand Builder Package",
          price: "$299",
          time: "/project",
          discountNote: "",
          features: [
            "Logo Design (3 concepts)",
            "Brand Style Guide",
            "Business Card, Social Media, and Email Signature Designs",
            "Presentation Template",
            "Print-Ready Marketing Collateral",
            "Optional Packaging Design",
          ],
          target:
            "Entrepreneurs and startups building or refreshing their brand identity",
        },
        {
          title: "Website Care Pro",
          price: "$299",
          time: "/month",
          discountNote: "",
          features: [
            "Regular Updates & Maintenance",
            "Security Monitoring & Bug Fixes",
            "Performance Optimization",
            "Plugin & Theme Updates",
            "Monthly Backup & Recovery",
            "Comprehensive SEO Strategy",
            "Keyword Research and Implementation",
            "Monthly Performance Reports",
            "Local SEO (for physical-location businesses)",
            "Up to 3 Backlink Opportunities",
            "Content Optimization",
            "Technical SEO Audits and Schema Markup",
          ],
          target:
            "Businesses focused on improving visibility and climbing search rankings",
        },
        {
          title: "Custom Package",
          price: "$5,000 ",
          start: "starting at",
          time: "/project",
          discountNote: "",
          features: [
            "Business Analysis & Strategy Development",
            "Dedicated Account Manager",
            "Monthly Check-ins & Adjustments",
            "Advanced Analytics & Reporting",
            "Campaign Management (Google, Facebook, Instagram)",
            "Personalized Team Training",
            "Direct Support via Email or Phone",
          ],
          target:
            "Businesses needing a fully customized digital growth strategy",
        },
      ],
    };
  },
};
</script>

<style scoped>
/* Container & layout */
.container {
  /* margin: 0 auto; */
  padding: 40px 20px;
}

.pricing-container {
  display: flex;
  flex-direction: column;
}

.column {
  display: flex;
  flex-direction: column;
  gap: 40px;
}

.pricing-card-wrapper {
  overflow-y: visible;
  /* padding-right: 10px; */
  gap: 20px;
  display: flex;
  flex-direction: column;
}

.pricing-card {
  display: flex;
  justify-content: space-between; /* put right content to the right side */
  gap: 10px;
  padding: 10px 10px;
  background: #fff;
  flex-direction: row-reverse;
  border-radius: 24px;
  border: none;
  background: #f7f6fc;
  position: relative;

  /* box-shadow: 0 8px 16px rgb(0 0 0 / 0.1); */
  /* transition: box-shadow 0.3s ease; */
}

/* Left features panel */
.left-cont {
  flex: 1;
  background: white;
  padding: 40px 35px;
  border-radius: 24px;
  color: #444;
  font-weight: 500;
  font-size: 1rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.left-cont ul {
  list-style: none;
  padding-left: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 14px;
}
.left-cont ul li {
  padding-left: 0;
  font-weight: 500;
  font-size: 1rem;
}

/* Right plan info panel */
.right-cont {
  /* flex-basis: 360px; */
  flex: 1;
  position: sticky;
  top: 20px;
  align-self: flex-start;
  background: white;
  padding: 30px 40px;
  border-radius: 24px;
  display: flex;
  flex-direction: column;
  gap: 24px;
  color: #222;
}

/* Plan title */
.title {
  display: flex;
  align-items: center;
  gap: 18px;
  font-weight: 700;
  font-size: 1.25rem;
  text-transform: uppercase;
  letter-spacing: 1.1px;
  color: black;
}
.circle {
  height: 48px;
  width: 48px;
  background: black;
  color: white;
  border-radius: 50%;
  font-weight: 900;
  font-size: 1.5rem;
  display: flex;
  justify-content: center;
  align-items: center;
  user-select: none;
}

/* Price section */
.price {
  display: flex;
  flex-direction: column;
  gap: 2px;
}

.sup-cont {
  display: flex;
  align-items: center;
  gap: 10px;
}

.start-text {
  font-size: 0.85rem;
  color: #666;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1.2px;
}

.current-cont {
  display: flex;
  align-items: flex-end;
  gap: 6px;
}

.current-price {
  font-size: 48px;
  font-weight: 900;
  color: black;
}

.price-time {
  font-size: 1rem;
  font-weight: 600;
  color: #888;
  margin-bottom: 4px;
}

/* Billing toggle buttons */
.period {
  margin-bottom: 12px;
}
.period button {
  padding: 10px 26px;
  margin-right: 12px;
  border: 2px solid white;
  background: transparent;
  color: black;
  font-weight: 700;
  font-size: 0.9rem;
  border-radius: 50px;
  cursor: pointer;
  transition: all 0.3s ease;
  user-select: none;
}
/* .period button:hover {
  background: #7e22ce;
  color: white;
} */
.period button.active {
  background: black;
  color: white;
  border-color: white;
}

/* Discount text */
.discount {
  color: #16a34a; /* bright green */
  font-weight: 600;
  font-size: 0.95rem;
}

/* Target text */
.target {
  font-size: 0.9rem;
  color: #444;
  line-height: 1.4;
  margin-top: auto;
  font-weight: 500;
}

/* Responsive */
@media (max-width: 800px) {
  .pricing-card {
    flex-direction: column;
    padding: 20px;
    gap: 30px;
  }

  .left-cont,
  .right-cont {
    padding: 24px;
    flex-basis: auto;
    width: 100%;
  }

  .right-cont {
    position: relative;
    top: auto;
    margin-top: 0;
  }

  .title {
    font-size: 1.1rem;
    gap: 12px;
  }

  .circle {
    height: 40px;
    width: 40px;
    font-size: 1.2rem;
  }

  .current-price {
    font-size: 36px;
  }

  .price-time {
    font-size: 0.95rem;
  }

  .period button {
    padding: 8px 20px;
    font-size: 0.85rem;
  }
}

</style>
