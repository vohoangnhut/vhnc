<template>
  <div class="hello">
    <div v-if="msg">
    <code>A ha hôm nay {{ msg }} như con đĩ í i ì i í i i ì à há</code>
    <br>
    <code>ĐĨ {{ msg | capitalize }}</code>
    </div>
    <div v-if="!msg">
      <code>VÕ HOÀNG NHỰT</code>
      <br>
      <code>+84382098099</code>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {  
    msg: String
  },
  filters: {
  capitalize: function (value) {
    if (!value) return ''
    value = value.toString()
    return value.toUpperCase();
  }
}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
</style>
