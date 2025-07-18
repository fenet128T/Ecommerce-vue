<template>
  <section class="py-12 scroll-mt-20 bg-gray-50" id="products">
  <main class="container mx-auto px-4">
  <header class="flex justify-between items-center mb-8">
    <h2 class="md:text-3xl text-2xl font-bold text-amber-900">Featured products</h2>
    <nav class="flex space-x-4" aria-label="product carousel controls">
        <button class="p-2 rounded-full bg-white shadow-md hover:bg-pink-100 text-pink-600 transition-colors" aria-label="previous slide">
            <Icon icon="line-md:arrow-small-left" width="24" height="24"/>
        </button>
          <button class="p-2 rounded-full bg-white shadow-md hover:bg-pink-100 text-pink-600 transition-colors" aria-label="new slide">
            <Icon icon="line-md:arrow-small-left" width="24" height="24"/>
        </button>
    </nav>
  </header>
  <section class="relative overflow-hidden">
    <ul class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
        <li class="bg-white rounded-lg shadow-md overflow-hidden transition-all duration-300 hover:scale-105"></li>
    </ul>
  </section>
  </main>
  </section>
</template>

<script setup>
 import {ref, computed,onMounted} from 'vue'
 const currentSlide=ref(0);
 const productPerPage=ref(4);
 const products=[
    {id:1,name:'Floral', price:99.99, rating:4.5,image:'../assets/product1.jpg',discount:20},
    {id:2,name:'Oriental', price:199.99, rating:4.9,image:'../assets/product2.jpg',discount:15},
    {id:3,name:'Woody', price:89.99, rating:4.5,image:'../assets/product3.jpg',discount:5},
    {id:4,name:'Floral', price:59.99, rating:4.8,image:'../assets/product4.jpg',discount:15},
    {id:5,name:'Floral', price:69.99, rating:4.5,image:'../assets/product5.jpg',discount:5},
    {id:6,name:'Floral', price:84.99, rating:4.4,image:'../assets/product6.jpg',discount:10},
    {id:7,name:'Floral', price:100.99, rating:4.2,image:'../assets/product7.jpg',discount:25},
    {id:8,name:'Floral', price:94.99, rating:4.1,image:'../assets/product8.jpg',discount:0},

 ]
 const totalSlide=computed(() => Math.ceil(products.length/productsPerPage.value));
 const visibleProducts=computed(() =>{
    const start = currentSlide.value*productsPerPage.value;
    return products.slice(start, start+productsPerPage.value)
 })
 const nextSlide=() =>{
    currentSlide.value=currentSlide.value
 }
 onMounted(() =>{
    
 })
</script>

