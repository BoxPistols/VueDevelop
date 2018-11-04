<template>
  <div class="hello">
    <h1>Are you like this?</h1>
    
    <button v-bind:class='{active:isActive}' v-on:click="toggle" v-show="tgl">{{ tgl }}</button>    
    <h2 v-show="showMsg">{{ msg }}</h2>
    <h2 v-show="showText">{{ tex }}</h2>
    <p>{{ count }}</p>
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      tgl: 'toggle',
      msg: 'Please like!',
      tex: 'Remove like...',
      showMsg: true,
      showText: false,
      count: 1,
    };
  },
  methods: {
    toggle: function() {
      this.showText = !this.showText;
      this.showMsg = !this.showMsg;
      this.count = this.count + 1;
      //       count = count + 1;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang='scss' scoped>
h1,
h2 {
  font-weight: normal;
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
button {
  padding: 10px 20px;
}
.active {
  color: red;
}
</style>
