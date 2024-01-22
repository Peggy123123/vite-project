<template>
  <div class="about">
    <div>{{ data }}</div>
    <h1>This is an about page</h1>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}

</style>

<script>
export default {
  data(){
    return {
      data:{}
    }
  },
  mounted(){
    console.log(import.meta.env.VITE_TEXT);
    
    const url = `import.meta.env.VITE_PATH` //改為環境變數
    this.$http.get(url)
    .then(res=>{
      console.log(res);
      this.data = res.data
    })
  }
}
</script>