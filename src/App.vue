<template>
  <div id="app">
    <component v-bind:is="which_to_show"></component>
  </div>
</template>

<script>
import first from "./components/first.vue"
import second from "./components/second.vue"
import third from "./components/third.vue"
import forth from "./components/forth.vue"
import fivth from "./components/fivth.vue"
import sixth from "./components/sixth.vue"
import seventh from "./components/seventh.vue"
import eighth from "./components/eighth.vue"

export default {
  data() {
    return {
      which_to_show: "first"
    }

  },
  components: {
    first,
    second,
    third,
    forth,
    fivth,
    sixth,
    seventh,
    eighth
  },
  mounted() {
    this.initComponent();
  },
  methods: {
    initComponent() {
      let _self = this;
      setInterval(function(){
        var index = _self.randomIndex();
        var arr = ["first", "second", "third", "forth", "fivth", "sixth", "seventh", "eighth"];
        console.log(arr[index - 1]);
        _self.which_to_show = arr[index - 1];
      }, 3000);
    },
    randomIndex() {
      return Math.ceil((Math.random() * 8));
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
