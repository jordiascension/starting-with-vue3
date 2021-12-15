<template>
  <form class="Rev" @submit.prevent="onSubmit">
    <h3>Leave a review</h3>
    <div class="form-group">
    <label for="name">Name:</label>
    <input id="name" v-model="name">
    </div>

    <div class="form-group">
    <label for="review">Review:</label>      
    <textarea id="review" v-model="review"></textarea>
    </div>

    <div class="form-group">
    <label for="rating">Rating:</label>
    <select id="rating" v-model.number="rating">
      <option>5</option>
      <option>4</option>
      <option>3</option>
      <option>2</option>
      <option>1</option>
    </select>
    </div>

    <input class="button" type="submit" value="Submit">
  </form>
</template>

<script>
export default {
    name: 'Rev',
    data: () => ({
        name: '',
        review: '',
        rating: null
    }),
    methods: {
    onSubmit() {
        let productReview = {
        name: this.name,
        review: this.review,
        rating: this.rating,
        }
        this.$emit('review-submitted', productReview)    
        alert(JSON.stringify(productReview))
        this.name = ''
        this.review = ''
        this.rating = null
        }
    }
}
</script>

<style>

</style>