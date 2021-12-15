<template>
  <div class="product-display">
      <div class="product-container">
      </div>
      <review-list :reviews="reviews"></review-list>
      <rev @review-submitted="addReview"></rev>
  </div>
</template>

<script>
import ReviewList from './ReviewList.vue';
import Rev from './Rev.vue';
export default {
    name: 'ProductDisplay',
    data: () => ({
        reviews: []
    }),
    methods:{
        addReview(review) {
            this.reviews.push(review)
        }
    },
    components:{
        ReviewList,
        Rev
    }

}
</script>

<style>

</style>