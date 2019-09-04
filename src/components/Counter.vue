<template>
  <div class="hello">
    <!-- <span>{{ msg }}</span> -->
    <button type="button" v-on:click="_add">+</button>
    <span>{{$store.getters.getNum(this.index)}}</span>
    <button type="button" v-on:click="_minus">-</button>
  </div>
</template>

<script>
export default {
  name: "Counter",
  props: {
    index: Number,
    msg: String
  },

  // data(){
  // return {
  //     counter:0
  // }
  // },

  methods: {
    _add: function() {
      this.$store.commit("add", this.index);
      console.log(this.$store.getters.getNum(this.index));
    },

    _minus: function() {
      this.$store.commit("sub", this.index);
    }
  }
};
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