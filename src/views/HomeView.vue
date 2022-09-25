<template>
  <div class="home">
    <TheProducts />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import TheProducts from '@/components/TheProducts.vue'

export default defineComponent({
  name: 'HomeView',
  components: {
    TheProducts,
  },
});
</script>
