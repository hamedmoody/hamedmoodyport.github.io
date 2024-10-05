<template>
  <HeaderHeader/>
  <HomeStatistic/>
  <SkillRates/>
  <HomeCourses/>
</template>

<script>
import HeaderHeader from "@/views/partials/home/HomeHeader.vue";
import HomeStatistic from "@/views/partials/home/HomeStatistic.vue";
import SkillRates from "@/views/partials/home/SkillRates.vue";
import HomeCourses from "@/views/partials/home/HomeCourses.vue";
export default {
  name: "HomeView",
  components: {HeaderHeader, HomeStatistic, SkillRates, HomeCourses},
  data() {
    return {

    }
  },

}
</script>

<style scoped lang="scss">


</style>