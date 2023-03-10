<script setup>
</script>

<template>
  <nav class="navbar navbar-expand-lg bg-body-tertiary">
    <div class="container-fluid">
      <router-link class="navbar-brand" to="/">
        <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-pokeball" width="16" height="16" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
          <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
          <path d="M12 12m-9 0a9 9 0 1 0 18 0a9 9 0 1 0 -18 0"></path>
          <path d="M12 12m-3 0a3 3 0 1 0 6 0a3 3 0 1 0 -6 0"></path>
          <path d="M3 12h6"></path>
          <path d="M15 12h6"></path>
        </svg>
        Vuemon
      </router-link>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav">
          <router-link class="nav-link" aria-current="page" to="/">Home</router-link>
          <router-link class="nav-link" to="about">About</router-link>

        </div>
      </div>
<!--      <div class="d-flex">-->
<!--        <a-->
<!--            href="javascript:void()"-->
<!--            class="btn ml-auto font-weight-bold"-->
<!--            id="theme-toggler"-->
<!--            onclick="toggleTheme()"-->
<!--        >🌙</a>-->
<!--      </div>-->
    </div>
  </nav>
  <div class="main">
    <router-view></router-view>
  </div>
  <footer class="bg-body-tertiary">
    <div>{{ new Date().getFullYear() }}</div>
  </footer>
</template>

<style>
footer {
  position: fixed;
  bottom: 0;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 26px;
}
</style>
