<template> 
  <div>

    <a>
        <img :src="imageSrc" class="item-image" alt="Placeholder image">
    </a>

    <div>    
      <p><a :href="urlLink">{{title}}</a></p>
      <p>{{ description }}</p>
      <div>
        <span v-for="tag in tags" v-bind:key="tag">{{tag}} <br> </span>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'PortfolioItem',
  props: {
    title: String,
    urlLink: String,
    imageSrc: String,
    description: String,
    tags: Array
  }
}
</script>

<style>
.item-image{
    width: 300px;
}
</style>
