<template>
  <div>
    <hello-world />
    <my-product />
  </div>
</template>

<script>
  import MyProduct from '@/components/MyProduct.vue'
  import HelloWorld from '../components/HelloWorld'

  export default {
    name: 'Home',

    components: {
      HelloWorld,
        MyProduct,
    },
  }
</script>
