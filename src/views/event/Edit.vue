<template>
  <!-- <h3>{{ event.name }}{{ event.surname }}</h3> -->
  <h4>Status:  {{ event.status }} </h4>
  <b>Vaccines</b><br>  
    First dose : {{ event.type }} <br>
    Second dose : {{ event.type2 }} <br>

  <!-- <button @click="edit"> Edit </button> -->
  <br>
  <button @click="Dcomment"> Doctor's comment </button>
  <br>
  <br>
</template>
<script>

export default {
  props: ['event'],
  inject: ['GStore'],
  methods: {
    Dcomment(){
      this.$router.push({
        name: 'DocComm',
        params: { id: this.event.id }
      })
      this.GStore.flashMessage2 = 'Comment from Doctor to ' + this.event.name
      setTimeout(() => {
        this.GStore.flashMessage2 = ''}
      ,3000)
    },
    // onSubmit() {
    //         if (this.name === '' || this.review ==='' ) {
    //             alert('Review is incomplete . Please fill out every field.')
    //             return
    //         }
    //         let productReview = {
    //             name: this.name,
    //             review: this.review,
      
    //         }
    //         this.$emit('review-submitted', productReview)
    //         this.name = '',
    //         this.review = ''
    //     },
    //     addReview(review){
    //       this.review.push(review)
    //     }
  },
  // reviews: {
  //           type: Array,
  //           required: true
  //       },
}
</script>