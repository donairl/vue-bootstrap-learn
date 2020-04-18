<template>
    <div class="page">
      <b-card title="Please enter">
       <BookForm msg="ga" />
      </b-card>

      <b-card title="Books" sub-title="List of Book">
          <b-table striped hover :items="books"></b-table>
      </b-card>    


    </div>   
</template>
<script>
import BookForm from '../components/BookForm.vue';


export default {
 name:'Book', 
 data(){
  return{
    books: null,
    
  }   
  
 }, 
 mounted(){
  this.onPageRefresh();
 },  
 components:
 {
   BookForm
 },
  methods:{

   onSubmit(){

   },
   onReset(){

   },
   onPageRefresh(){
       this.$axios.get('http://localhost:3000/books').then(response => {
          this.books = response.data
          console.log(this.books)
        })
        .catch(error => {
          console.log(error)
          this.errored = true
        })
        .finally(() => this.loading = false)

   }
 }
}
</script>