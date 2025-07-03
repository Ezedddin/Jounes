<script setup lang="ts">
import { ref } from 'vue'

// Contact form data
const contactForm = ref({
  naam: '',
  email: '',
  bericht: ''
})

const isSubmitting = ref(false)

const submitForm = async () => {
  isSubmitting.value = true
  
  try {
    // Formspree endpoint - vervang YOUR_FORM_ID door je echte Formspree form ID
    const formspreeEndpoint = 'https://formspree.io/f/mwpbzqag'
    
    // Prepare form data for Formspree
    const formData = {
      name: contactForm.value.naam,
      email: contactForm.value.email,
      message: contactForm.value.bericht,
      _subject: `Contact bericht van ${contactForm.value.naam} - JOCHRUNZ`,
      _replyto: contactForm.value.email
    }
    
    // Echte Formspree verzending
    const response = await fetch(formspreeEndpoint, {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
      },
      body: JSON.stringify(formData)
    })
    
    if (!response.ok) {
      throw new Error('Formspree verzending mislukt')
    }
    
    alert(`✅ Bedankt ${contactForm.value.naam}! Je bericht is succesvol verzonden naar kamelezeddin@gmail.com via Formspree. We nemen zo snel mogelijk contact met je op!`)
    
    // Reset form
    contactForm.value = { naam: '', email: '', bericht: '' }
    
  } catch (error) {
    console.error('Email verzenden mislukt:', error)
    alert(`❌ Sorry ${contactForm.value.naam}, er ging iets mis. Probeer het opnieuw of bel ons direct op +32 483 85 93 12.`)
  } finally {
    isSubmitting.value = false
  }
}
</script>

<template>
  <section id="contact" class="contact">
    <div class="container">
      <h2 class="section-title">Neem Contact Op</h2>
      <p class="contact-subtitle">Heb je vragen of wil je een speciale bestelling? Bel ons op +32 483 85 93 12 of +32 485 75 45 66, mail naar Jochrunz@gmail.com, of gebruik het formulier hieronder!</p>
      <form @submit.prevent="submitForm" class="contact-form">
        <div class="form-row">
          <div class="form-group">
            <label for="naam">Naam</label>
            <input 
              type="text" 
              id="naam" 
              v-model="contactForm.naam" 
              required 
              placeholder="Je naam"
              :disabled="isSubmitting"
            >
          </div>
          <div class="form-group">
            <label for="email">E-mail</label>
            <input 
              type="email" 
              id="email" 
              v-model="contactForm.email" 
              required 
              placeholder="je@email.com"
              :disabled="isSubmitting"
            >
          </div>
        </div>
        <div class="form-group">
          <label for="bericht">Bericht</label>
          <textarea 
            id="bericht" 
            v-model="contactForm.bericht" 
            required 
            placeholder="Vertel ons wat je op je hart hebt..."
            rows="5"
            :disabled="isSubmitting"
          ></textarea>
        </div>
        <button type="submit" class="submit-button" :disabled="isSubmitting">
          <span v-if="isSubmitting">📧 Versturen...</span>
          <span v-else>Verstuur Bericht</span>
        </button>
      </form>
      
    </div>
  </section>
</template>

<style scoped>
.contact {
  padding: 80px 0;
  background: linear-gradient(135deg, #F5F5DC 0%, #FDF5E6 100%);
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

.section-title {
  font-family: 'Fredoka', sans-serif;
  font-size: 2.8rem;
  font-weight: 700;
  color: #FF69B4;
  text-align: center;
  margin-bottom: 20px;
  text-shadow: 1px 1px 3px rgba(255, 105, 180, 0.2);
}

.contact-subtitle {
  text-align: center;
  font-size: 1.2rem;
  color: #666;
  margin-bottom: 50px;
}

.contact-form {
  max-width: 600px;
  margin: 0 auto;
  background: white;
  padding: 40px;
  border-radius: 25px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.form-row {
  display: flex;
  gap: 20px;
  margin-bottom: 25px;
}

.form-group {
  flex: 1;
}

.form-group label {
  display: block;
  font-family: 'Fredoka', sans-serif;
  font-weight: 600;
  color: #333;
  margin-bottom: 8px;
  font-size: 1.1rem;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 15px;
  border: 2px solid #FFB6C1;
  border-radius: 15px;
  font-family: 'Comic Neue', cursive;
  font-size: 1rem;
  transition: all 0.3s ease;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #FF69B4;
  box-shadow: 0 0 10px rgba(255, 105, 180, 0.3);
}

.submit-button {
  background: linear-gradient(135deg, #FF69B4 0%, #FF1493 100%);
  color: white;
  font-family: 'Fredoka', sans-serif;
  font-size: 1.2rem;
  font-weight: 600;
  padding: 15px 40px;
  border: none;
  border-radius: 25px;
  cursor: pointer;
  transition: all 0.3s ease;
  width: 100%;
  margin-top: 20px;
}

.submit-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 5px 20px rgba(255, 105, 180, 0.4);
}

@media (max-width: 768px) {
  .form-row {
    flex-direction: column;
  }
}

/* Setup Info Styling */
.setup-info {
  max-width: 600px;
  margin: 40px auto 0;
  padding: 30px;
  background: #FFF8DC;
  border-radius: 20px;
  border: 2px solid #FFD700;
  text-align: left;
}

.setup-info h3 {
  font-family: 'Fredoka', sans-serif;
  color: #FF69B4;
  margin-bottom: 15px;
  font-size: 1.3rem;
}

.setup-info p {
  color: #666;
  margin-bottom: 15px;
  font-size: 1rem;
}

.setup-info ol {
  color: #333;
  padding-left: 20px;
}

.setup-info li {
  margin-bottom: 8px;
  line-height: 1.5;
}

.setup-info a {
  color: #FF69B4;
  text-decoration: none;
  font-weight: 600;
}

.setup-info a:hover {
  text-decoration: underline;
}

/* Disabled state styling */
.submit-button:disabled {
  opacity: 0.7;
  cursor: not-allowed;
  transform: none !important;
}

.form-group input:disabled,
.form-group textarea:disabled {
  opacity: 0.6;
  cursor: not-allowed;
  background-color: #f5f5f5;
}

@media (max-width: 480px) {
  .section-title {
    font-size: 2.2rem;
  }
  
  .setup-info {
    margin: 30px auto 0;
    padding: 20px;
  }
}
</style> 