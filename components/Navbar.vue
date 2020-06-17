<template>
  <div class="nav">
    <nuxt-link to="/" class="nav-link">Real world Events</nuxt-link>
    <nav>
      <nuxt-link to="/" class="nav-link">List</nuxt-link>
      <nuxt-link to="/event/create" class="nav-link">Create</nuxt-link>
    </nav>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss">
.nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 70px;
  background: rgb(220, 248, 214);
  &-link {
    padding: 0 20px;
    text-decoration: none;
    font-size: 20px;
    font-weight: 500;
  }
}
</style>
