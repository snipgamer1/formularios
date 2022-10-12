<template>
  <div class="container mt-3">
    <Header />

    <Formulario />


    

  </div>

  
  
</template>
<script>
import Header from "./components/Header.vue";
import Formulario from "./components/Formulario.vue";
  
  export default {
    data: () => ({
        url: "https://cdn.svgporn.com/logos/vue.svg",
        des: "Vue.js",
    }),
    
    components: {
      Header,
      Formulario
    },
};
</script>