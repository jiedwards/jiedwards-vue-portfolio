<template>
  <div class="card">
    <h5 class="card-title">{{ title }}</h5>
    <div class="container-fluid">
      <img id="projectImg" class="card-img-top" :src="imageSrc" alt="Card image cap" />
    </div>
    <div class="card-body">
      <p class="card-text">
        {{ description }}
      </p>

      <a :href="`https://github.com/jiedwards/${title}`">
        <img
          id="githubRepoImg"
          border="0"
          alt="GitHub Repository"
          src="../assets/github.svg"
        />
      </a>
    </div>
    <div class="card-footer">
      <small class="text-muted">Last updated 3 mins ago</small>
    </div>
  </div>
</template>

<script>
export default {
  name: "PortfolioItem",
  props: {
    title: String,
    urlLink: String,
    imageSrc: String,
    description: String,
    tags: Array,
  },
};
</script>

<style>
img#projectImg {
  width: 300px;
}
img#githubRepoImg { 
  width: 50px;
  height: 50px;
}
</style>
