<template>
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <div class="container-fluid">
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item">
          <nuxt-link class="nav-link active" aria-current="page" to="counter">Counter</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" aria-current="page" to="v-for-arr">v-for array</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" aria-current="page" to="v-for-obj">v-for object</nuxt-link>
        </li>

      </ul>
    </div>
  </div>
</nav>
</template>

<script>
export default {

}
</script>

<style>

</style>