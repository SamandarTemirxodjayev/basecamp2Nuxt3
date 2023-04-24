<template>
  <div class="container">
    <div class="text-3xl" @click="setLocalstorage">
      Set LocalStorage
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    setLocalstorage() {
      if(process.client) {
        localStorage.setItem('login_id', 'Jerry')
        this.$router.push('/')
      }
    }
  },
  created() {
    if(process.client) {
      const id = localStorage.getItem('login_id')
      if(id){
        this.$router.push('/')
      }
    }
  }
}


</script>

<style>

</style>