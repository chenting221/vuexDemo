<template>
  <div class="hello">
    <h2>{{count}}</h2>
    <h2>{{getStateCount}}</h2>
    <hr>
    <p>count的值{{count}}</p>
    <button @click="addFun">+</button>
    <button @click="reductionFun">-</button>
  </div>
</template>

<script>
import { mapState, mapGetters } from 'vuex'
export default {
  name: 'HelloWorld',
  data () {
    return {}
  },
  computed: {
    ...mapState({
      count: state => state.count
    }),
    ...mapGetters(['getStateCount'])
  },
  methods: {
    addFun: function () {
      this.$store.dispatch('addFun')
    },
    reductionFun: function () {
      this.$store.dispatch('reductionFun')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
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
</style>
