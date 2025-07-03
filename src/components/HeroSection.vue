<template>
  <section id="home" class="hero">
    <div class="hero-wrapper">
      <div class="hero-content">
        <h2 class="hero-title">De lekkerste snoepjes aan huis bezorgd!</h2>
        <p class="hero-subtitle">Ontdek onze wereld vol kleurrijk en heerlijk snoep</p>
        <button class="cta-button">Bekijk Assortiment</button>
      </div>
      <div class="hero-image">
        <img src="https://images.unsplash.com/photo-1514066558159-fc8c737ef259?w=600&h=400&fit=crop&crop=center" alt="Kleurrijk snoep">
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  background: linear-gradient(135deg, #FFE4E6 0%, #FFF0F5 50%, #F8F8FF 100%);
  padding: 80px 0;
  width: 100%;
  display: block;
  position: relative;
}

.hero-wrapper {
  max-width: 1200px;
  width: 100%;
  margin: 0 auto;
  padding: 0 20px;
  box-sizing: border-box;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 60px;
}

.hero-content {
  flex: 1;
  max-width: 500px;
}

.hero-title {
  font-family: 'Fredoka', sans-serif;
  font-size: 3.5rem;
  font-weight: 700;
  color: #FF69B4;
  margin-bottom: 20px;
  line-height: 1.2;
  text-shadow: 2px 2px 4px rgba(255, 105, 180, 0.2);
}

.hero-subtitle {
  font-size: 1.3rem;
  color: #666;
  margin-bottom: 30px;
  font-weight: 400;
}

.cta-button {
  background: linear-gradient(135deg, #FF69B4 0%, #FF1493 100%);
  color: white;
  font-family: 'Fredoka', sans-serif;
  font-size: 1.2rem;
  font-weight: 600;
  padding: 15px 35px;
  border: none;
  border-radius: 50px;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(255, 105, 180, 0.4);
}

.cta-button:hover {
  transform: translateY(-3px);
  box-shadow: 0 6px 25px rgba(255, 105, 180, 0.6);
}

.hero-image {
  flex: 1;
  max-width: 500px;
}

.hero-image img {
  width: 100%;
  height: 400px;
  object-fit: cover;
  border-radius: 30px;
  box-shadow: 0 10px 30px rgba(255, 105, 180, 0.3);
  transition: transform 0.3s ease;
}

.hero-image img:hover {
  transform: scale(1.05);
}

@media (max-width: 768px) {
  .hero-wrapper {
    flex-direction: column;
    text-align: center;
    gap: 40px;
  }
  
  .hero-title {
    font-size: 2.5rem;
  }
}

@media (max-width: 480px) {
  .hero-title {
    font-size: 2rem;
  }
}
</style> 