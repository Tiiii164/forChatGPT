<script>
import NavBar from '@/Components/NavBar.vue';
import theFooter from '@/Components/TheFooter.vue';
export default {
  components: {
      NavBar,
      theFooter,
  },
  data() {
    return {
      currentUser: {},
    }
},
  created() {
      this.getCurrentUser()
},
  methods: {
    getCurrentUser() {
      axios.get('/getCurrentUser')
        .then(response => { 
          this.currentUser = response.data
        }
      )
      .catch(error => { console.log(error) }
      )
  },
},
} 
</script>
<template>
  <NavBar></NavBar>
    <div class="container">
      <div class="jumbotron mt-5">
          <div class="col-sm-8 mx-auto">
            <h1 class="text-center"> Welcome <span class="text-success">{{ currentUser.name }}</span> <span class="text-success"></span></h1>
          </div>
        </div>
    </div>
    <theFooter></theFooter>
  </template>
  
  