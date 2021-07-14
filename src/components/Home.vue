<template>
  <div>
    <ul class="shadow-2xl">
      <p class="p-4 shadow text-xl">Ludovic Spina</p>
      <li><a class="active" href="#home">Accueil</a></li>
      <li><a href="#about">A propos</a></li>
      <li><a href="#">Résumé</a></li>
      <li><a href="#">Portefolio</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Home"
}
</script>

<style scoped>

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  width: 13%;
  background-color: #2F3253;
  position: fixed;
  height: 100%;
  overflow: auto;
  color: white;
}

li a {
  display: block;
  padding: 8px 16px;
  text-decoration: none;
}

li a.active {
  background-color: #161B33;
  color: white;
}

li a:hover:not(.active) {
  background-color: #161B33;
  color: white;
}
</style>