<template>
  <div v-if="isLoading === true">Loading...</div>
  <div v-if="hasError === true">Error</div>
  <div v-else>
      <div class="container" v-for="project in data" v-bind:key="project.id">
        <PortfolioItem
          :title="project.name"
          :urlLink="project.html_url"
          :imageSrc="require(`../assets/project_images/${project.name}/${project.name}.gif`)"
          :description="project.description"
          :tags="project.topics"
        >
        </PortfolioItem>
      </div>
  </div>
</template>

<script>
import PortfolioItem from "./PortfolioItem.vue";
import axios from "axios";
export default {
  name: "PortfolioProjectContainer",
  components: {
    PortfolioItem,
  },
  data() {
    return {
      data: null,
      isLoading: true,
      hasError: false,
    };
  },
  mounted() {
    axios
      .get("https://api.github.com/users/jiedwards/repos", {
        headers: {
          Accept: "application/vnd.github.mercy-preview+json",
        },
      })
      .then(
        (response) => (
        this.data = response.data.filter(project => {
          return (
          project.name === 'shopping-haven' || 
          project.name === 'lyrical-ly' ||
          project.name === 'films-db' ||
          project.name === 'tour-de-man-met' ||
          project.name === 'vehicle-db' ||
          project.name === 'cvChat'
        )})
      ))
      .catch((error) => {
        console.log(error);
        this.hasError = true;
      })
      .finally(() => (this.isLoading = false));
  },
};
</script>

<style>
.grid {
  display: flex;
}
.col {
  flex: 1;
}
</style>