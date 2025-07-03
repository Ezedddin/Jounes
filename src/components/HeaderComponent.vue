<template>
  <header class="header">
    <div class="container">
      <div class="logo-section">
        <img src="/src/assets/logo.JPG" alt="JOCHRUNZ Logo" class="logo">
        <h1 class="brand-name">JOCHRUNZ</h1>
      </div>
      <nav class="nav">
        <a href="#home" class="nav-link">Home</a>
        <a href="#about" class="nav-link">Over Ons</a>
        <a href="#products" class="nav-link">Assortiment</a>
        <a href="#contact" class="nav-link">Contact</a>
      </nav>
    </div>
  </header>
</template>

<style scoped>
.header {
  background: linear-gradient(135deg, #FFB6C1 0%, #FFE4E6 50%, #FFF0F5 100%);
  padding: 1rem 0;
  box-shadow: 0 4px 20px rgba(255, 182, 193, 0.3);
  position: sticky;
  top: 0;
  z-index: 100;
  width: 100%;
  display: block;
}

.container {
  max-width: 1200px;
  width: 100%;
  margin: 0 auto;
  padding: 0 20px;
  box-sizing: border-box;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo-section {
  display: flex;
  align-items: center;
  gap: 15px;
}

.logo {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  border: 3px solid #FF69B4;
  transition: transform 0.3s ease;
}

.logo:hover {
  transform: scale(1.1) rotate(10deg);
}

.brand-name {
  font-family: 'Fredoka', sans-serif;
  font-size: 2.2rem;
  font-weight: 700;
  color: #FF69B4;
  text-shadow: 2px 2px 4px rgba(255, 105, 180, 0.3);
}

.nav {
  display: flex;
  gap: 30px;
}

.nav-link {
  text-decoration: none;
  color: #FF69B4;
  font-weight: 600;
  font-size: 1.1rem;
  padding: 10px 20px;
  border-radius: 25px;
  transition: all 0.3s ease;
  position: relative;
}

.nav-link:hover {
  background: rgba(255, 105, 180, 0.1);
  transform: translateY(-2px);
  color: #E91E63;
}

@media (max-width: 768px) {
  .container {
    flex-direction: column;
    gap: 20px;
  }
  
  .nav {
    gap: 15px;
  }
  
  .nav-link {
    font-size: 1rem;
    padding: 8px 15px;
  }
}

@media (max-width: 480px) {
  .brand-name {
    font-size: 1.8rem;
  }
}
</style> 