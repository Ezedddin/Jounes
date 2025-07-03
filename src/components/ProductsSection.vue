<script setup lang="ts">
import { ref, computed } from 'vue'

// Product categories and data
const selectedCategory = ref('all')

const categories = [
  { id: 'all', name: 'Alle Producten', icon: '🍭' },
  { id: 'chocolade', name: 'Chocolade', icon: '🍫' },
  { id: 'snoep', name: 'Snoep', icon: '🍬' },
  { id: 'drinken', name: 'Drinken', icon: '🥤' },
  { id: 'kauwgom', name: 'Kauwgom', icon: '🫧' },
  { id: 'koekjes', name: 'Koekjes', icon: '🍪' },
  { id: 'mix', name: 'Mix & Mystery', icon: '🎁' }
]

const allProducts = [
  // Chocolade
  {
    id: 1,
    name: 'Dubai Chocolate',
    price: '€ 10,00',
    category: 'chocolade',
    image: 'https://images.unsplash.com/photo-1606312619070-d48b4c652a52?w=300&h=300&fit=crop&crop=center'
  },
  {
    id: 2,
    name: 'Mister Beast Chocolate',
    price: '€ 3,00',
    category: 'chocolade',
    image: 'https://m.media-amazon.com/images/I/61rXXviigEL.jpg'
  },
  
  // Snoep
  {
    id: 3,
    name: 'Mentos',
    price: '€ 1,50',
    category: 'snoep',
    image: 'https://static.wikia.nocookie.net/the_candy_encyclopedia/images/8/80/Mentos.jpg/revision/latest?cb=20200516172032'
  },
  {
    id: 4,
    name: 'Lolipop',
    price: '€ 1,00',
    category: 'snoep',
    image: 'https://i.ebayimg.com/images/g/yEcAAOSw9LlalEm2/s-l1200.jpg'
  },
  {
    id: 5,
    name: 'Candy Bubble Gum',
    price: '€ 2,00',
    category: 'snoep',
    image: 'https://cottoncravings.com/wp-content/uploads/2024/07/bubblegum.jpg'
  },
  {
    id: 7,
    name: 'Sour Patch Kids',
    price: '€ 3,50',
    category: 'snoep',
    image: 'https://cdn.webshopapp.com/shops/263312/files/439899917/sour-patch-kids-sour-patch-kids-original-pouch-130.jpg'
  },
  {
    id: 8,
    name: 'Airhead',
    price: '€ 2,75',
    category: 'snoep',
    image: 'https://mycandystore.nl/cdn/shop/files/AirheadsBlueRaspberry.jpg?v=1696445215'
  },

  // Drinken
  {
    id: 9,
    name: 'Pepsi Cola 33CL',
    price: '€ 2,50',
    category: 'drinken',
    image: 'https://images.unsplash.com/photo-1629203851122-3726ecdf080e?w=300&h=300&fit=crop&crop=center'
  },
  {
    id: 6,
    name: 'Tropico',
    price: '€ 2,50',
    category: 'drinken',
    image: 'https://prod.isg.bruneau.media/asset/aHR0cHM6Ly9icnVuZWF1LnNpbXBsZXdvcmtzcGFjZS5uZXQvZmlsZS9wdWJBc3NldEJhc2UvS2doNV9jc0FWX1hOR1Fmd3hsVDVtbXVycVVtaDk4Y1hZcnlJdzFfd2ZPbU9PZGRHNU5ZLzAvcy83NzM4NDAuanBn/?quality=85'
  },
  {
    id: 10,
    name: 'Mentos Drink',
    price: '€ 2,00',
    category: 'drinken',
    image: 'https://www.unitedsweets.co.nz/cdn/shop/files/MentosGreen_1024x1024.png?v=1717999422'
  },
  {
    id: 11,
    name: 'AA Drink Orange',
    price: '€ 3,00',
    category: 'drinken',
    image: 'https://balvismeesters.nl/wp-content/uploads/2020/11/AA-drink-TinyJPG.jpg'
  },
  {
    id: 12,
    name: 'Gatorade',
    price: '€ 3,50',
    category: 'drinken',
    image: 'https://www.farsons.com/en/file.aspx?f=1526'
  },

  // Kauwgom
  {
    id: 13,
    name: '50 PCS Aardbei',
    price: '€ 5,00',
    category: 'kauwgom',
    image: 'https://media.s-bol.com/NrwgWlzmpq8K/v2kgzOr/1200x1007.jpg'
  },
  {
    id: 14,
    name: 'Mentos 28 PCS',
    price: '€ 3,50',
    category: 'kauwgom',
    image: 'https://static.ah.nl/dam/product/AHI_4354523130313031363132?revLabel=1&rendition=400x400_JPG_Q85&fileType=binary'
  },

  // Koekjes
  {
    id: 15,
    name: 'Oreo Original',
    price: '€ 3,00',
    category: 'koekjes',
    image: 'https://dutchshopper.com/cdn/shop/files/891863_3a68e9fb-0def-491a-b2a5-74a4eb3561ef.png?v=1736659459'
  },
  {
    id: 16,
    name: 'Oreo Wafer Rolls',
    price: '€ 3,50',
    category: 'koekjes',
    image: 'https://www.myamericanshop.nl/cdn/shop/products/oreo-wafer-roll-chocolate-8934680033442-31484365144227.png?v=1704731846'
  },

  // Mix & Mystery
  {
    id: 17,
    name: 'Snoep Mix S',
    price: '€ 5,00',
    category: 'mix',
    image: 'https://notenleverancier.nl/cdn/shop/files/D773D2DC-1778-4476-B257-538074F8DA7C.jpg?v=1707328516'
  },
  {
    id: 18,
    name: 'Snoep Mix M',
    price: '€ 8,00',
    category: 'mix',
    image: 'https://notenleverancier.nl/cdn/shop/files/D773D2DC-1778-4476-B257-538074F8DA7C.jpg?v=1707328516'
  },
  {
    id: 19,
    name: 'Snoep Mix L',
    price: '€ 12,00',
    category: 'mix',
    image: 'https://notenleverancier.nl/cdn/shop/files/D773D2DC-1778-4476-B257-538074F8DA7C.jpg?v=1707328516'
  },
  {
    id: 20,
    name: 'Mystery Box S',
    price: '€ 10,00',
    category: 'mix',
    image: 'https://snoepbeer.nl/app/uploads/2024/08/download-8.jpg'
  },
  {
    id: 21,
    name: 'Mystery Box M',
    price: '€ 15,00',
    category: 'mix',
    image: 'https://snoepbeer.nl/app/uploads/2024/08/download-8.jpg'
  },
  {
    id: 22,
    name: 'Mystery Box L',
    price: '€ 20,00',
    category: 'mix',
    image: 'https://snoepbeer.nl/app/uploads/2024/08/download-8.jpg'
  }
]

// Computed property for filtered products
const filteredProducts = computed(() => {
  if (selectedCategory.value === 'all') {
    return allProducts
  }
  return allProducts.filter(product => product.category === selectedCategory.value)
})

// Function to set category
const setCategory = (categoryId: string) => {
  selectedCategory.value = categoryId
}
</script>

<template>
  <section id="products" class="products">
    <div class="container">
      <h2 class="section-title">Ons Snoep Assortiment</h2>
      <p class="section-subtitle">Ontdek alle lekkernijen uit onze snoepwinkel</p>
      
      <!-- Category Filter -->
      <div class="category-filter">
        <button 
          v-for="category in categories" 
          :key="category.id"
          @click="setCategory(category.id)"
          :class="['category-btn', { active: selectedCategory === category.id }]"
        >
          <span class="category-icon">{{ category.icon }}</span>
          <span class="category-name">{{ category.name }}</span>
        </button>
      </div>

      <!-- Products Grid -->
      <div class="products-grid">
        <div 
          v-for="product in filteredProducts" 
          :key="product.id" 
          class="product-card"
        >
          <div class="product-image">
            <img :src="product.image" :alt="product.name">
          </div>
          <h3 class="product-name">{{ product.name }}</h3>
          <p class="product-price">{{ product.price }}</p>
          <button class="add-to-cart">Bestellen</button>
        </div>
      </div>

      <!-- Contact Info -->
      <div class="contact-info">
        <h3>Bestellen?</h3>
        <p>📱 Bel ons: <strong>+32 483 85 93 12</strong></p>
        <p>📱 Of: <strong>+32 485 75 45 66</strong></p>
        <p>📧 Email: <strong>Jochrunz@gmail.com</strong></p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.products {
  padding: 80px 0;
  background: linear-gradient(135deg, #F0F8FF 0%, #E6F3FF 100%);
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

.section-subtitle {
  text-align: center;
  font-size: 1.2rem;
  color: #666;
  margin-bottom: 40px;
}

/* Category Filter */
.category-filter {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 15px;
  margin-bottom: 50px;
}

.category-btn {
  display: flex;
  align-items: center;
  gap: 8px;
  background: white;
  border: 3px solid #FFB6C1;
  border-radius: 25px;
  padding: 12px 20px;
  font-family: 'Fredoka', sans-serif;
  font-weight: 600;
  color: #FF69B4;
  cursor: pointer;
  transition: all 0.3s ease;
  font-size: 1rem;
}

.category-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 15px rgba(255, 105, 180, 0.3);
}

.category-btn.active {
  background: linear-gradient(135deg, #FF69B4 0%, #FF1493 100%);
  color: white;
  border-color: #FF69B4;
}

.category-icon {
  font-size: 1.2rem;
}

.category-name {
  font-size: 1rem;
}

/* Products Grid */
.products-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 30px;
  margin-bottom: 60px;
}

.product-card {
  background: white;
  border-radius: 25px;
  padding: 25px;
  text-align: center;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
  border: 3px solid transparent;
  position: relative;
}

.product-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 40px rgba(255, 105, 180, 0.2);
  border-color: #FFB6C1;
}

.product-image {
  width: 200px;
  height: 200px;
  margin: 0 auto 20px;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.product-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.product-card:hover .product-image img {
  transform: scale(1.1);
}

.product-name {
  font-family: 'Fredoka', sans-serif;
  font-size: 1.4rem;
  font-weight: 600;
  color: #333;
  margin-bottom: 20px;
}

.product-price {
  font-size: 1.3rem;
  font-weight: 700;
  color: #FF69B4;
  margin-bottom: 20px;
}

.add-to-cart {
  background: linear-gradient(135deg, #32CD32 0%, #228B22 100%);
  color: white;
  font-family: 'Fredoka', sans-serif;
  font-weight: 600;
  padding: 12px 25px;
  border: none;
  border-radius: 25px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-size: 1rem;
  width: 100%;
}

.add-to-cart:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 15px rgba(50, 205, 50, 0.4);
}

/* Contact Info */
.contact-info {
  background: white;
  border-radius: 25px;
  padding: 30px;
  text-align: center;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
  border: 3px solid #FFB6C1;
}

.contact-info h3 {
  font-family: 'Fredoka', sans-serif;
  font-size: 1.8rem;
  color: #FF69B4;
  margin-bottom: 20px;
}

.contact-info p {
  font-size: 1.1rem;
  color: #333;
  margin-bottom: 10px;
}

.contact-info strong {
  color: #FF69B4;
  font-weight: 700;
}

/* Responsive Design */
@media (max-width: 768px) {
  .category-filter {
    gap: 10px;
  }
  
  .category-btn {
    padding: 10px 16px;
    font-size: 0.9rem;
  }
  
  .category-name {
    display: none;
  }
  
  .products-grid {
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 20px;
  }
}

@media (max-width: 480px) {
  .section-title {
    font-size: 2.2rem;
  }
  
  .products-grid {
    grid-template-columns: 1fr;
  }
  
  .category-filter {
    justify-content: flex-start;
    overflow-x: auto;
    padding-bottom: 10px;
  }
}
</style> 