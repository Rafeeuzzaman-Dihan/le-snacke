<script setup>
import { ref } from 'vue'

// Categories
const categories = [
  'Burgers',
  'Pizza',
  'Desserts',
  'Drinks',
  'Starters',
  'Specials',
  'Healthy',
  'Favorites',
  'Combos'
]

const menuItems = {
  Burgers: [
    { name: 'Classic Burger', price: '$5.99', description: 'A delicious classic burger with fresh lettuce, tomato, and cheese.' },
    { name: 'Cheese Burger', price: '$6.99', description: 'Juicy beef patty topped with melted cheddar cheese.' },
    { name: 'Bacon Burger', price: '$7.99', description: 'Crispy bacon, fresh veggies, and our special sauce.' },
    { name: 'Veggie Burger', price: '$5.49', description: 'Grilled veggie patty with fresh salad.' },
    { name: 'Double Patty', price: '$8.99', description: 'Two juicy beef patties with double cheese.' }
  ],
  Pizza: [
    { name: 'Margherita', price: '$8.99', description: 'Classic pizza with tomato sauce, mozzarella, and basil.' },
    { name: 'Pepperoni', price: '$9.99', description: 'Loaded with pepperoni slices and extra cheese.' },
    { name: 'Veggie Pizza', price: '$9.49', description: 'Fresh vegetables and mozzarella cheese.' },
    { name: 'BBQ Chicken', price: '$10.99', description: 'BBQ sauce, chicken pieces, and cheese.' }
  ],
  Desserts: [
    { name: 'Chocolate Cake', price: '$4.99', description: 'Rich chocolate cake with fudge icing.' },
    { name: 'Ice Cream', price: '$3.99', description: 'Creamy ice cream in multiple flavors.' },
    { name: 'Cheesecake', price: '$5.49', description: 'Classic cheesecake with a buttery crust.' },
    { name: 'Brownie', price: '$3.49', description: 'Chocolate brownie with nuts.' }
  ],
  Drinks: [
    { name: 'Coca Cola', price: '$1.99', description: 'Chilled soft drink.' },
    { name: 'Orange Juice', price: '$2.49', description: 'Freshly squeezed orange juice.' },
    { name: 'Lemonade', price: '$1.99', description: 'Refreshing lemonade.' },
    { name: 'Iced Tea', price: '$2.29', description: 'Cold brewed iced tea.' }
  ],
  Starters: [
    { name: 'French Fries', price: '$2.99', description: 'Crispy golden fries.' },
    { name: 'Chicken Wings', price: '$5.99', description: 'Spicy grilled chicken wings.' },
    { name: 'Spring Rolls', price: '$4.49', description: 'Crispy veggie spring rolls.' },
    { name: 'Garlic Bread', price: '$3.49', description: 'Toasted garlic bread.' }
  ],
  Specials: [
    { name: 'Chef Special Pasta', price: '$9.99', description: 'Pasta with special chef sauce.' },
    { name: 'Seafood Platter', price: '$14.99', description: 'Assorted seafood with dips.' },
    { name: 'Steak', price: '$12.99', description: 'Grilled steak cooked to perfection.' },
    { name: 'Grilled Salmon', price: '$13.99', description: 'Fresh salmon with herbs.' }
  ],
  Healthy: [
    { name: 'Caesar Salad', price: '$5.99', description: 'Crispy lettuce with Caesar dressing.' },
    { name: 'Fruit Bowl', price: '$4.99', description: 'Seasonal fresh fruits.' },
    { name: 'Grilled Chicken Salad', price: '$7.49', description: 'Grilled chicken with greens.' },
    { name: 'Quinoa Bowl', price: '$6.99', description: 'Healthy quinoa with veggies.' }
  ],
  Favorites: [
    { name: 'Burger Combo', price: '$8.99', description: 'Classic burger with fries and drink.' },
    { name: 'Pizza Combo', price: '$11.99', description: 'Medium pizza with drink.' },
    { name: 'Dessert Platter', price: '$9.49', description: 'Assorted desserts for sharing.' }
  ],
  Combos: [
    { name: 'Family Combo', price: '$19.99', description: '2 pizzas, 4 drinks, and 1 dessert.' },
    { name: 'Couple Combo', price: '$12.99', description: '1 pizza, 2 drinks, and 1 dessert.' },
    { name: 'Snack Combo', price: '$7.99', description: 'Fries, nuggets, and soft drink.' }
  ]
}

const activeCategory = ref('Burgers')
const selectCategory = (category) => activeCategory.value = category
</script>

<template>
  <section class="py-12 px-6 max-w-6xl mx-auto">

    <!-- Categories -->
    <div class="flex flex-wrap gap-6 justify-center mb-12 border-b border-gray-200 pb-4">
      <button
          v-for="cat in categories"
          :key="cat"
          @click="selectCategory(cat)"
          class="relative px-3 py-1 text-[18px] font-800 transition-colors group"
          :class="activeCategory === cat ? 'text-[#FEF1D8]' : 'text-gray-700 hover:text-[#FEF1D8]'"
      >
        {{ cat }}
        <span
            class="absolute left-0 -bottom-1 h-1 bg-[#FEF1D8] transition-all duration-300"
            :class="activeCategory === cat ? 'w-full' : 'w-0 group-hover:w-full'"
        ></span>
      </button>
    </div>

    <!-- Menu Items -->
    <div class="flex flex-col gap-6">
      <div
          v-for="item in menuItems[activeCategory]"
          :key="item.name"
          class="flex flex-col gap-1"
      >
        <div class="flex justify-between items-start">
          <h3 class="text-lg font-semibold text-gray-800">{{ item.name }}</h3>
          <p class="text-amber-400 font-medium">{{ item.price }}</p>
        </div>
        <p class="text-gray-500 mt-1 line-clamp-2">{{ item.description }}</p>
      </div>
    </div>

  </section>
</template>

<style scoped>
button {
  position: relative;
}
button span { width: 0; }
button:hover span { width: 100%; }
</style>