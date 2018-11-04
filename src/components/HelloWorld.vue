<template>
  <div class="hello">    
    <h1>Are you like this?</h1>    
    
    <div class="org_likeArea" v-on:click="toggle" v-show="tgl">
      <h2 v-show="showMsg">{{ msg }}</h2>
      <h2 v-show="showText">{{ tex }}</h2>

      <transition>
      <div v-bind:class='{active:isActive}' v-if="this.showText">
        <p class="m_like add">♡ {{ count + 1 }}</p>
      </div>
      <div v-else>
        <p class="m_like">♡ {{ count }}</p>
      </div>
      </transition>  
    </div>        
  
  </div>
</template>

<script>
export default {
  data() {
    return {
      tgl: 'toggle',
      msg: 'Please like!',
      tex: 'Remove like...',
      isActive: true,
      showMsg: true,
      showText: false,
      count: 1,
    };
  },
  methods: {
    toggle: function() {
      this.showText = !this.showText;
      this.showMsg = !this.showMsg;
      //       this.count = this.count;
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
.org_likeArea {
  background: #eee;
  cursor: pointer;
}
button.btn {
  padding: 15px 20px;
}
.active p {
  color: red;
}

.m_like {
  font-size: 20px;
  transition: 0.3s;
  &.add {
    font-size: 30px;
  }
}
</style>
