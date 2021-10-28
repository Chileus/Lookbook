<template>
  <a class="link">
    <img @mouseover="hover = true" @mouseleave="hover = false" class="image01" src="~/assets/image01.jpg">
    <transition name="fade" >
      <div class="hover" v-if="hover">

        <button> zoomin </button>
      </div>
    </transition>
    <span>
      <button v-on:click="counter +=1"> HYPE </button>
      <div class="counter"> {{counter}} </div>
    </span>
    <div class="hover-text">
      <h1> New street Wear Style {{id}}</h1>
      <p> 5 dagen geleden </p>
      <h3> Items: </h3>
      <ul>
        <li> Jean Atelier Patchwork star Denim Jacktet </li>
        <li> Jean Atelier Patchwork star Denim Jacktet </li>
        <li> Jean Atelier Patchwork star Denim Jacktet </li>
        <li> Jean Atelier Patchwork star Denim Jacktet </li>
        <li> Jean Atelier Patchwork star Denim Jacktet </li>
      </ul>
    </div>
  </a>
</template>

<script>
  export default{
    props: {
      id: 0
    },
    name: "hello world",
    data(){
      return{
        pictureStatic: require("~/assets/image01.jpg"),
        hover: false,
        counter: 0
      }
    }
  }
</script>

<style>
.fade-enter-active, .fade-leave-active {
  transition: .5s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}

img{
  width:300px;
  height: 400px;
  padding: 20px;
  object-fit: cover;
  object-position: 10% 0;
  transition: 0.5s;
}

.link{
  position:relative;
}
span{
  display: flex;
  width: 70px;
  justify-content: space-evenly;
  position: absolute;
  bottom: 10%;
  margin-left: 40px;
}
button, .counter{
  color:black;
  background-color: white;
  border: 1px solid black;
  padding: 5px;
  border-radius: 5px;
}

img:hover{
  -webkit-filter: brightness(50%);
}
img div{
  position: relative;
}

.hover{
  pointer-events: none;
  position: absolute;
  top: 10%;
  width: 100%;
  margin-left: 20px;
  padding: 20px;
  color: white;
}
.hover-text ul{
  padding: 0;
  list-style: none;
}
.hover-text h1{
  position: relative;
  top: 20px;
  font-size: 20px;
}
.hover-text h3{
  font-size: 16px;
}
.hover-text li{
  text-decoration: none;
  font-size: 12px;
}

</style>
