<template>
  <div class="contact-section">
    <div class="contact-inner">
      <div class="left-pane">
        <h2>Need a custom quote?</h2>
        <p>Don’t let your ideas sit idle—slide into our inbox and let’s make magic!</p>
      </div>

      <div class="form-box">
        <form>
          <div class="form-row">
            <input type="text" placeholder="Your Name" />
          </div>

          <div class="form-row double">
            <input type="text" placeholder="Your Email" />
            <input type="text" placeholder="Phone Number" />
          </div>

          <div class="form-row">
            <input type="text" placeholder="Subject" />
          </div>

          <div class="form-row">
            <input type="text" placeholder="Your Budget (USD)" />
          </div>

          <div class="form-row">
            <textarea rows="5" placeholder="Tell us about your project..."></textarea>
          </div>

          <div class="form-row">
            <button type="submit">Send Message</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>
<style>
   .contact-section {
  display: flex;
  justify-content: center;
  padding: 120px 20px;
  position: relative;
  /* background: #0a0a0a; */
}

.contact-inner {
  display: flex;
  width: 100%;
  max-width: 1200px;
  gap: 40px;
  position: relative;
}

.left-pane {
  flex: 1.3;
  padding: 60px 40px;
  background: orangered;
  border-radius: 20px;
  color: white;
  z-index: 1;
  min-height: 800px;
  max-width: 800px;
}

.form-box {
  flex: 0.85;
  background: #111;
  border: 1px solid rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(20px);
  padding: 40px;
  border-radius: 20px;
  color: white;
  z-index: 2;
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.4);
  width: calc(50% + 100px);
  position: absolute;
  top: 15%;
  left: 55%;
  transform: translateX(-50%);
}

/* Form styling */
form {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.form-row {
  width: 100%;
}

.double {
  display: flex;
  gap: 10px;
}

.double input {
  flex: 1;
}

input,
textarea {
  width: 100%;
  padding: 14px 18px;
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 14px;
  font-size: 1rem;
  color: white;
  outline: none;
}

input::placeholder,
textarea::placeholder {
  color: rgba(255, 255, 255, 0.6);
}

button {
  background: white;
  color: #111;
  border: none;
  padding: 14px 20px;
  border-radius: 14px;
  font-weight: 600;
  cursor: pointer;
  font-size: 1rem;
  transition: 0.3s ease;
}

button:hover {
  background: #e6e6e6;
}
@media (max-width: 1024px) {
  .contact-inner {
    flex-direction: column;
    align-items: center;
  }

  .left-pane {
    width: 100%;
    min-height: auto;
  }

  .form-box {
    position: static;
    width: 100%;
    margin-top: -40px; /* slight overlap feel */
    transform: none;
  }
}


</style>