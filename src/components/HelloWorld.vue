<template>
  <div class="hello">
    My Changes....
    <img alt="Vue logo" src="../assets/spider-verse/spider-verse.jpg" height='250px'>
    <multiverse />
  </div>
</template>

<script>
import multiverse from '@/components/MultiVerse.vue';
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  components: {
    multiverse
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
