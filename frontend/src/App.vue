<template>
  <div id="app">
    <header class="header">
    <h1>
    <router-link v-bind:to="{name: 'about-us'}"><img class="mealTimeLogo" src="./assets/MealTime 3.png"></router-link>
    </h1>
    <div id="nav" class="fake-btn">
      <router-link class="btn-fix-class" id="home" v-bind:to="{ name: 'home' }">HOME </router-link >
      <router-link class="btn-fix-class" id="all-recipes" v-bind:to="{ name: 'all-recipes' }"> ALL RECIPES </router-link>
      <router-link class="btn-fix-class" id="saved-recipes" v-bind:to="{ name: 'saved-recipes', params: { userID: this.$store.state.user.id } }"> MY RECIPES </router-link>
      <router-link class="btn-fix-class" id="meal-plan" v-bind:to="{ name: 'meal-plan', params: { userID: this.$store.state.user.id } }"> MY MEAL PLAN </router-link> 
      <router-link class="btn-fix-class" id="user-grocery-list" v-bind:to="{ name: 'user-grocery-list', params: { userID: this.$store.state.user.id } }"> MY GROCERY LIST </router-link> 
      <router-link class="btn-fix-class" v-bind:to="{ name: 'logout' }" v-if="$store.state.token != ''"> LOGOUT</router-link>
    </div>
     </header>
     
    <router-view />
   
  </div>
</template>
<script>
</script>

<style>
#app{
  background-image: linear-gradient(to bottom right, antiquewhite, #2fcee1, #A56EFA);
  min-height: 100vh;
  background-size: cover !important;
  font-family: Arial, Helvetica, sans-serif;
}
h1{
  font-size: 40px;
  padding-left: 10px;
  padding-top: 10px;
}
#nav {
  font-size: 18px;
  height: 100%;
  text-align: right;
  border-bottom: 2px solid black;
  padding-right: 10px;
  padding-bottom:10px;
  display:flex;
  justify-content: flex-end;
  
}
.btn-fix-class{
  position:static;
  border:1px solid black;
  text-decoration: none;
  color: darkblue;
  text-align: right;
  padding: 5px 10px;
  background-color: aliceblue;
  border-radius: 10px;
  visibility:initial;
  display: inline-block;
}
.btn-fix-class:hover{
  background-color: orange;
}

.mealTimeLogo {
  margin-bottom: -65px;
}

.loading {
  display: flex;
  justify-content: center;
  align-items: center;
  animation-delay: 5s;
  animation-duration: 5s;
}

</style>