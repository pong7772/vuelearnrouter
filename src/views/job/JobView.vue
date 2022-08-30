<template>
  <h1>job</h1>
  <div class="wrapper" v-for="job in jobList" :key="job.id">
    <router-link :to="{ name: 'jobDetail', params: { id: job.id } }">
      <div class="title">{{ job.title }}</div>
      <div>{{ job.detail }}</div>
    </router-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      jobList: [
        { title: "Ux UI", id: 1, detail: "good at ui" },
        { title: "App Ux UI", id: 2, detail: "good at ui" },
        { title: "web Ux UI", id: 3, detail: "good at ui" },
      ],
    };
  },
};
</script>

<style scoped>
.wrapper {
  background: rgb(100, 97, 97);
  margin: 10px;
  padding: 20px;
  text-align: center;
  border-radius: 10px;
  cursor: pointer;
}
.wrapper:hover {
  background: rgba(255, 255, 255, 0.557);
}
.title {
  color: white;
  font-size: large;
}
</style>