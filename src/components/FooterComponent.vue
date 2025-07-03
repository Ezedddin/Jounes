<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-section">
          <h3>JOCHRUNZ</h3>
          <p>De lekkerste snoepjes voor iedereen!</p>
        </div>
        <div class="footer-section">
          <h4>Links</h4>
          <a href="#home">Home</a>
          <a href="#about">Over Ons</a>
          <a href="#products">Assortiment</a>
          <a href="#contact">Contact</a>
        </div>
        <div class="footer-section">
          <h4>Contact</h4>
          <p>📧 info@jochrunz.nl</p>
          <p>📞 06-12345678</p>
        </div>
      </div>
      <div class="footer-bottom">
        <p>&copy; 2024 JOCHRUNZ. Alle rechten voorbehouden. Gemaakt met ❤️ en heel veel snoep!</p>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: linear-gradient(135deg, #4B0082 0%, #8B008B 100%);
  color: white;
  padding: 50px 0 20px;
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

.footer-content {
  display: flex;
  justify-content: space-between;
  gap: 40px;
  margin-bottom: 30px;
}

.footer-section h3,
.footer-section h4 {
  font-family: 'Fredoka', sans-serif;
  margin-bottom: 15px;
  color: #FFB6C1;
}

.footer-section a {
  color: #E6E6FA;
  text-decoration: none;
  display: block;
  margin-bottom: 8px;
  transition: color 0.3s ease;
}

.footer-section a:hover {
  color: #FFB6C1;
}

.footer-bottom {
  text-align: center;
  padding-top: 20px;
  border-top: 1px solid rgba(255, 182, 193, 0.3);
  color: #E6E6FA;
}

@media (max-width: 768px) {
  .footer-content {
    flex-direction: column;
    text-align: center;
  }
}
</style> 