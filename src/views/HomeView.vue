<template>
  <HeaderHeader/>
  <HomeStatistic/>
  <SkillRates/>
</template>

<script>
import HeaderHeader from "@/views/partials/home/HomeHeader.vue";
import HomeStatistic from "@/views/partials/home/HomeStatistic.vue";
import SkillRates from "@/views/partials/home/SkillRates.vue";
export default {
  name: "HomeView",
  components: {HeaderHeader, HomeStatistic, SkillRates},
  data() {
    return {

    }
  },

}
</script>

<style scoped lang="scss">


</style>