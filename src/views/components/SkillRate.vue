<template>
  <div class="rate">
    <picture>
      <img :src="icon" alt="">
    </picture>
  </div>
</template>

<script>
export default {
  name  : "SkillRate",
  props : {
    icon: {
      type: String,
    }
  }
}
</script>

<style scoped>

</style>