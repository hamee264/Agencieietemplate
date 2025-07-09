<template>
  <div class="container">
    <div class="img-container left">
      <img src="/src/assets/showreelimg.avif" alt="Image 1" />
    </div>
    <div class="video-container">
      <video controls
        autoplay
        muted
        loop
        playsinline
        src="/src/assets/7noJ6ZABGBxwSX8scPjAZOqcOhU.mp4"
      ></video>
    </div>
    <div class="img-container right">
      <img src="/src/assets/showreelimg2.avif" alt="Image 2" />
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.container {
  display: flex;
  width: 100%;
  height: 100vh;
  overflow: hidden;
  padding: 100px 30px;
  gap: 10px;
  transition: all 0.6s ease;
}

.img-container,
.video-container {
  flex: 1;
  overflow: hidden;
  transition: all 0.6s ease;
}

.img-container img,
.video-container video {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  border-radius: 10px;
}

/* === HOVER EFFECT ON DESKTOP === */
.container:hover .video-container {
  flex: 3;
}

.container:hover .img-container {
  flex: 0;
  opacity: 0;
  pointer-events: none;
}

/* === RESPONSIVENESS === */
@media (max-width: 768px) {
  .container {
    flex-direction: column;
    height: auto;
    padding: 20px;
  }

  .img-container,
  .video-container {
    flex: unset;
    height: 200px;
    opacity: 1 !important;
    pointer-events: auto;
  }

  .container:hover .video-container,
  .container:hover .img-container {
    flex: unset;
  }

  .img-container img,
  .video-container video {
    border-radius: 8px;
  }
}
</style>
