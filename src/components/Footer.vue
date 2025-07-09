<template>
  <footer class="agencie-footer">
    <div class="footer-content">
      <div class="footer-top">
        <div class="footer-brand">
          <h1>Agencie.co</h1>
          <p>The next big thing starts here—<br />drop us a line and let’s get creating!</p>
        </div>

        <div class="footer-links">
          <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">Benefits</a></li>
            <li><a href="#">Portfolio</a></li>
            <li><a href="#">Reviews</a></li>
            <li><a href="#">About</a></li>
          </ul>
          <ul>
            <li><a href="#">LinkedIn</a></li>
            <li><a href="#">Facebook</a></li>
            <li><a href="#">Twitter</a></li>
            <li><a href="#">Instagram</a></li>
            <li><a href="#">YouTube</a></li>
          </ul>
        </div>
      </div>

      <div class="footer-divider"></div>

      <div class="footer-grid">
        <div class="footer-column">
          <p class="label">Phone</p>
          <p>(217) 555–0134</p>
        </div>
        <div class="footer-column">
          <p class="label">Email</p>
          <p>agencie@email.com</p>
        </div>
        <div class="footer-column">
          <p class="label">Address</p>
          <p>123 Main Street, Suite 200, Austin, TX 78701</p>
        </div>
        <div class="footer-column">
          <p class="label">Opening Hours</p>
          <p>Mon - Fri, 9am - 5pm</p>
        </div>
      </div>

      <div class="footer-divider"></div>

      <div class="footer-bottom">
        <p>©Template by RealMehedi</p>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.agencie-footer {
  background-color: #0a0a0a;
  color: white;
  padding: 80px 20px 40px;
  font-family: 'Inter', sans-serif;
}

.footer-content {
  max-width: 1200px;
  margin: auto;
}

.footer-top {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 40px;
}

.footer-brand h1 {
  font-size: 3rem;
  color: #ff5a3c;
  font-weight: 800;
  margin-bottom: 20px;
}

.footer-brand p {
  font-size: 1.1rem;
  color: #ddd;
  max-width: 400px;
  line-height: 1.6;
}

.footer-links {
  display: flex;
  gap: 60px;
}

.footer-links ul {
  list-style: none;
  padding: 0;
}

.footer-links li {
  margin-bottom: 10px;
}

.footer-links a {
  text-decoration: none;
  color: #ffb199;
  font-weight: 500;
  transition: color 0.3s ease;
}

.footer-links a:hover {
  color: white;
}

.footer-divider {
  margin: 40px 0;
  height: 1px;
  background-color: #222;
}

.footer-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 30px;
  margin-bottom: 30px;
}

.footer-column .label {
  color: #ff5a3c;
  font-weight: 600;
  margin-bottom: 8px;
  text-transform: uppercase;
  font-size: 0.85rem;
}

.footer-column p {
  color: #eee;
  line-height: 1.6;
  font-size: 1rem;
}

.footer-bottom {
  text-align: left;
  font-size: 0.9rem;
  color: #777;
}
</style>
