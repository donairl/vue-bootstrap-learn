<template>
  <div class="page-content">
    <b-card title="Please enter">
      <b-form @submit="onSubmit" @reset="onReset" >
         <b-form-group
        id="input-group-1"
        label="Username:"
        label-for="input-1"
        description="Your username."
       >
        <b-form-input
          id="input-1"
          v-model="user.username"
          type="text"
          required
          placeholder="Enter email"
        ></b-form-input>

      </b-form-group>
      
        <b-form-group
        id="input-group-1"
        label="Password:"
        label-for="input-1"
        description="Your username."
       >
        <b-form-input
          id="input-1"
          v-model="user.password"
          type="password"
          required
          placeholder="Enter Password"
        ></b-form-input>
           <b-button type="submit" variant="primary">Login</b-button>
            &nbsp;
            <b-button type="reset" variant="danger">Reset</b-button>
            <b-button type="button" variant="secondary" @click="onClickRead">Read</b-button>
      </b-form-group>
      </b-form>    
 
   
  </b-card>

  <p>&nbsp;</p>
   <div>
    <b-table striped hover :items="users"></b-table>
  </div>
  </div>
</template>

<script>


export default {
  data() {
    return {
      users: null,
      user: {
        username: '',
        password: '',
        
      },
    }
  },
  mounted(){
     this.onClickRead();  
  },
  methods: {
    onClickRead() {


      this.$axios
        .get('http://localhost:3000/users')
        .then(response => {
          this.users = response.data
          console.log(this.users)
        })
        .catch(error => {
          console.log(error)
          this.errored = true
        })
        .finally(() => this.loading = false)


    },
    onSubmit(evt) {
      evt.preventDefault()
      console.log(JSON.stringify(this.user))
       
       this.$axios
        .get('http://localhost:3000/users?username='+this.username+'&password='+this.password)
        .then(response => {
          this.users = response.data
          console.log(this.users)
        })
        .catch(error => {
          console.log(error)
          this.errored = true
        })
        .finally(() => this.loading = false)

    },
    onReset(evt) {
      evt.preventDefault()
      // Reset our form values
      this.user.username = ''
      this.user.password = ''
      this.$nextTick(() => {
        // this.show = true
      })
    }
  }
}

</script>
