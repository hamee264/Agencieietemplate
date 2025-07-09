<template>
  <div class="container">
    <div class="card">
      <img src="/src/assets/showreelimg.avif" alt="Magnus" />
      <h3>Magnus Hawthorne</h3>
      <p>Owner, Bayleaf</p>
    </div>
    <div class="card">
      <img src="/src/assets/showreelimg.avif" alt="Magnus" />
      <h3>Thaddeus Montgomery</h3>
      <p>Owner, GoldGarden</p>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.container {
  padding:80px 30px;
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}

.card {
  flex: 1 1 250px;
  max-width: 600px;
 padding: 20px;
  display: flex;
  flex-direction: column;
  text-align: center;
  align-items: center;
  background: #f5f7f9;
  border-radius: 12px;
  overflow: hidden;
  
}

.card img {
  width: 100%;
  height: auto;
  object-fit: cover;
  max-height: 400px;
  padding-bottom: 20px;
}
h3{
    font-weight: 500;
}
p{
    font-weight: 500;
    font-size: smaller;
    color:gray;
}
</style>
