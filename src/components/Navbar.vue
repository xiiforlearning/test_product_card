<template>
  <nav class="grey lighten-5">
    <div class="nav-wrapper">
      <router-link to="/" class="brand-logo">Product Card</router-link>
      <ul id="nav-mobile" class="right hide-on-med-and-down">
        <router-link 
          tag="li"
          to="/"
          exact
          active-class="active"
        >
          <a href="#">Home</a>
        </router-link>

        <router-link 
          tag="li"
          to="/cardPage"
          active-class="active"
        >
          <a href="#">Card</a>
        </router-link>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  
}
</script>

<style lang="scss" scoped>
  * {
    color: #212121;
  }
  nav {
    position: fixed;
    top: 0;
    right: 0;
    left: 0;
    z-index: 1030;
    padding: 0 2rem;
  }
  .brand-logo {
    color: #212121;
    white-space: nowrap;
  }
</style>