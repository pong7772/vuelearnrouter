<script >
export default {
  methods: {
    handleBack() {
      this.$router.go(-1);
    },
    handleForword() {
      this.$router.go(1);
    },
    handleRedirect() {
      this.$router.push({ name: "home" });
    },
  },
};
</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
        <router-link to="/about">About</router-link>
        <router-link to="/">Home</router-link>
        <router-link :to="{ name: 'job' }">Jobs</router-link>
      </nav>
    </div>
  </header>

  <button class="btns" @click="handleRedirect">Redirect</button>
  <button class="btns" @click="handleForword">Forword</button>
  <button class="btns" @click="handleBack">Back</button>

  <router-view />
</template>

<style scoped>
.btns {
  cursor: pointer;
  width: 100px;
  padding: 10px;
  border: none;
  margin: 20px 10px;
  border-radius: 10px;
}
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
