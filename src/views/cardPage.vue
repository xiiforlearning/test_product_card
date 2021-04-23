<template>
  <div class="card-page">
      <Card 
        title="100% органический 10 лет корень корейского женьшеня красный Panax улучшить иммунную" 
        v-bind:rating=4.5
        v-bind:ratingsNum=243
        v-bind:ordersCount=1
        v-bind:price=20000000
        v-bind:discount=25
        v-bind:amount=1245
        v-bind:productPics="['01.png', '04.png', '03.png', '02.png',  '01.png', '04.png', '04.png']"
      />
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