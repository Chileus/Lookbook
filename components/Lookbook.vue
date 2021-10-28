<template>
  <div class="container">
    <div class="lookbook-container">
      <Picture v-for="post in posts" :id="post.id" />
    </div>
  </div>
</template>

<script>
export default{
  data:() => ({
    posts:[]
  }),
  async fetch(){
    this.posts = await this.$http.$get('https://fakestoreapi.com/products')
  }
}
</script?

<style>
.container{
  margin: 0 auto;
  width: 80vw;
  display: flex;
  align-content: center;
}
.lookbook-container{
  padding: 20px;
  display: flex;
	flex-direction: row;
	flex-wrap: wrap;
  align-content: flex-start;
}

</style>
