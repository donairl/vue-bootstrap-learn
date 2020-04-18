<template>
    <b-form @submit="onSubmit" @reset="onReset" >

       <b-form-group  id="input-group-1" label="Author:"  label-for="input-1" description="Author of the book">
        <b-form-input id="input-1" v-model="book.Author"
          type="text"
          required
          placeholder="Enter Author"
        ></b-form-input>

      </b-form-group>
        <b-form-group  id="input-group-2" label="Title:"  label-for="input-1" description="Title of the book">
        <b-form-input id="input-1" v-model="book.title"
          type="text"
          required
          placeholder="Enter Author"
        ></b-form-input>

      </b-form-group>
      
      <b-form-group  id="input-group-1" label="Price:"  label-for="input-1" description="Price of the book">
        <b-form-input id="input-1" v-model="book.price"
          type="text"
          required
          placeholder="Enter Price"
        ></b-form-input>
         <b-form-checkbox
              id="checkbox-bestseller"
              v-model="book.bestseller"
              name="checkbox-bestseller"
              value="true"
              unchecked-value="false"
            >
      Best Seller
    </b-form-checkbox>    
      </b-form-group>
      
      </b-form>   
</template>
<script>
export default {
  name: 'BookForm',
  data(){
   return  {
     book:{
        Author:'',
        title: '',
        price: '',
        bestseller: false
     
     }
     
   }
  },
  methods:{

   onSubmit(){

   },
   onReset(){

   }
   
  }
  
}
</script>