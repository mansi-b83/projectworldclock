<template>

    <div class="heroblock">
      <v-carousel hide-delimiters cycle height = "350px">
        <v-carousel-item
          v-for="(item,i) in items"
          :key="i"
          :src="item.src"
          reverse-transition="fade-transition"
          transition="fade-transition"
        ></v-carousel-item>
      </v-carousel>
    </div>
</template>

<script>
  export default {
    name: 'Hero',

    data: () => ({
       
        items: [
          {
            src: require("../assets/cimg1.jpg"),
          },
          {
            src: require("../assets/cimg2.jpg"),
          },
         
        ],
      
    }),
  }
</script>
