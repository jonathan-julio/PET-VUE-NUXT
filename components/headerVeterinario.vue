<template>
  <div class="sidebar text-center">
    <h1>

      <span >My Pet</span>
    </h1>
    <div id="itens">
        <a>Minhas consultas -> </a>
        <a><nuxt-link to="/veterinario/abertas">Abertas </nuxt-link></a>
        <a><nuxt-link to="/veterinario/aceitas">Aceitas </nuxt-link></a>
        <a><nuxt-link to="/veterinario/recusadas">Recusadas </nuxt-link></a>
        <a><nuxt-link to="/">Sair </nuxt-link></a>
    </div>
  </div>
</template>

<style>
:root {
  --sidebar-bg-color: #2f855a;
  --sidebar-item-hover: #38a169;
  --sidebar-item-active: #276749;
}
</style>

<style scoped>
.sidebar {
    align-items: center;
    color: white;
    background-color: var(--sidebar-bg-color);
    display: flex;
}
.sidebar a{
    text-decoration: none;
    color: white;
    padding: 0.5em;
}
.sidebar h1 {
  margin-left: 2.5em;
  margin-right: 40%;
}
@media (max-width: 1150px){
    .sidebar h1 {
        margin-left: 2.5em;
        margin-right: 20%;
    }
}
@media (max-width: 850px){
    h1{
        font-size: 25px;
    }
    .sidebar{
        padding-left: 0px;
        padding: 0.5em;
    }
    #itens{
        margin-left: 2ch;
        font-size: 15px;
    }
}
@media (max-width: 585px){
    h1{
        display: none;
    }
    .sidebar{
        padding-left: 0px;
        padding: 0.5em;
    }
    #itens{
        margin-left: 4ch;
        font-size: 15px;
    }
}
</style>
