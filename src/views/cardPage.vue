<template>
  <div class="card-page">
      <Card />
  </div>
</template>

<script>
import Card from '@/components/Card.vue'
export default {
  name: 'cardPage',
  components: {Card},
};
</script>

<style lang="scss" scoped>
  .card-page {
    margin-top: 64px;
  }
</style>