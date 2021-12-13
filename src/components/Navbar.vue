<template>
  <div class="navbar">
    <div class="logo">
      <router-link to="/">
        EFOSA.
      </router-link>
    </div>
    <div class="menu">
      <div></div>
      <div></div>
      <div></div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
.navbar {
  padding: 1.2rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #f2f5fa;
  box-shadow: 8px 10px 12px hsl(0deg 0% 61% / 20%);
}

.navbar .logo a {
  text-decoration: none;
  font-size: 2.2rem;
  font-weight: 700;
  color: #023E8A;
}

.menu {
  display: flex;
  flex-direction: column;
  visibility: hidden;
}

.menu div {
  height: 3px;
  width: 25px;
  background-color: #023E8A;
  margin: .15rem 0;
}
</style>