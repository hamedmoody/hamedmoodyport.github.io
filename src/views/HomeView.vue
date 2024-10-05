<template>
  <Header></Header>
  <HomeStatistic/>

</template>

<script>
import Header from "@/views/partials/home/HomeHeader.vue";
import HomeStatistic from "@/views/partials/home/HomeStatistic.vue";
export default {
  name: "HomeView",
  components: {Header, HomeStatistic},
  data() {
    return {

    }
  },

}
</script>

<style scoped lang="scss">


</style>