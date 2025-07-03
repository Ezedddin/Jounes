<template>
  <section id="about" class="about">
    <div class="container">
      <div class="about-content">
        <div class="about-text">
          <h2 class="section-title">Over JOCHRUNZ</h2>
          <p class="about-description">
            Het allemaal begon toen mijn kleine neefje Jounes een grote droom had: de hele wereld blij maken met de lekkerste snoepjes! 
            Met zijn grote glimlach en oneindige energie begon hij zijn eigen snoepavontuur. 
          </p>
          <p class="about-description">
            Van kleurrijke gummiberen tot de zuurste wormpjes - bij JOCHRUNZ vind je alle snoep die je hart begeert. 
            We geloven dat snoep niet alleen lekker moet zijn, maar ook een glimlach op je gezicht moet toveren!
          </p>
          <div class="fun-facts">
            <div class="fact">
              <span class="fact-number">1000+</span>
              <span class="fact-text">Tevreden klanten</span>
            </div>
            <div class="fact">
              <span class="fact-number">50+</span>
              <span class="fact-text">Snoepsoorten</span>
            </div>
            <div class="fact">
              <span class="fact-number">100%</span>
              <span class="fact-text">Glimlachen</span>
            </div>
          </div>
        </div>
        <div class="about-image">
          <img src="https://images.unsplash.com/photo-1579783902614-a3fb3927b6a5?w=500&h=600&fit=crop&crop=center" alt="Gelukkige kinderen met snoep">
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
  padding: 80px 0;
  background: linear-gradient(135deg, #FFF8DC 0%, #FFFACD 100%);
  width: 100%;
  display: block;
  position: relative;
}

.container {
  max-width: 1200px;
  width: 100%;
  margin: 0 auto;
  padding: 0 20px;
  box-sizing: border-box;
}

.about-content {
  display: flex;
  align-items: center;
  gap: 60px;
}

.about-text {
  flex: 1;
}

.section-title {
  font-family: 'Fredoka', sans-serif;
  font-size: 2.8rem;
  font-weight: 700;
  color: #FF69B4;
  margin-bottom: 30px;
  text-shadow: 1px 1px 3px rgba(255, 105, 180, 0.2);
}

.about-description {
  font-size: 1.2rem;
  color: #555;
  margin-bottom: 25px;
  line-height: 1.8;
}

.fun-facts {
  display: flex;
  gap: 40px;
  margin-top: 40px;
}

.fact {
  text-align: center;
}

.fact-number {
  display: block;
  font-family: 'Fredoka', sans-serif;
  font-size: 2.5rem;
  font-weight: 700;
  color: #FF69B4;
}

.fact-text {
  font-size: 1rem;
  color: #666;
  font-weight: 600;
}

.about-image {
  flex: 1;
  max-width: 400px;
}

.about-image img {
  width: 100%;
  height: 500px;
  object-fit: cover;
  border-radius: 25px;
  box-shadow: 0 10px 30px rgba(255, 105, 180, 0.2);
}

@media (max-width: 768px) {
  .about-content {
    flex-direction: column;
    text-align: center;
  }
  
  .fun-facts {
    justify-content: center;
    gap: 20px;
  }
}

@media (max-width: 480px) {
  .section-title {
    font-size: 2.2rem;
  }
}
</style> 