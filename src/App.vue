<template>
  <div id="app">
    <div>
      <b-navbar type="dark" variant="dark">
        <b-navbar-nav>
          <router-link to="/" class="container">
           <b-navbar-brand to="/"><h3> Gunpla shop</h3></b-navbar-brand>
          </router-link>
        </b-navbar-nav>
        <b-navebar-nav class="ml-auto">
          <div>
            <router-link to="/basketa">
              <b-button variant="info" @click="sum"
                >ตะกร้า
                <b-icon icon="basket" aria-hidden="ture"></b-icon>
              </b-button>
            </router-link>
          </div>
        </b-navebar-nav>
      </b-navbar>
      <div class="mt-3">
  </div>
    </div>
    <router-view />
  </div>
</template>

<script>
import { mapMutations } from "vuex";
export default {
  methods: {
    ...mapMutations(["sum"]),
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
