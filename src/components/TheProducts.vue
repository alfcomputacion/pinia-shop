<template>
  <div class="container bg-dark">
        <h1 class="card-item">Productos</h1>
    <div v-if="products.length > 0" class="card bg-primary">
        <p v-for="product in products" :key="product.idproducto">
        <img :src="product.imagen" alt="product image">
            {{product.nombre}}
        </p>
    </div>
    <div v-if="error" class="error">
        <p>{{ error }}</p>
    </div>

  </div>
</template>

<script>
import { ref } from 'vue'
export default {
    setup() {
        const products = ref([])
        const error = ref(null)

        const load = async () =>{
            let data = await fetch('https://soft.alfcomputacion.com/productos/')
            if(!data.ok){
                throw Error('No data available...')
            }
            products.value = await data.json()
    
        }
        load()
    
        return { products, error }
    }

}
</script>

<style>
img{
    height: 15rem;
}
</style>