<template>
  <nav class="nav-pane">
    <header>
      <ul>
        <li>
          <RouterLink to="/" class="logo-link">
            <img
              alt="app logo"
              class="logo"
              src="@/assets/kanbeast_logo.svg"
              width="30"
              height="30"
            />
          </RouterLink>
        </li>

        <li><RouterLink to="/about">About</RouterLink></li>
        <li><RouterLink to="/dashboard">Dashboard</RouterLink></li>
      </ul>
    </header>
  </nav>
</template>

<script>
export default {
  name: 'NavPanel'
}
</script>

<style scoped>
.nav-pane {
  display: flex;
  justify-content: soace-around;
  background-color: #7e819c;
  padding: 10px;
  position: fixed;
  top: 0px;
  width: 100%;
}
.nav-pane ul {
  display: flex;
  list-style-type: none;
  margin: 0;
  padding: 0;
}
.nav-pane ul li {
  margin: 0 0.5rem;
}
</style>
