<template>
  <b-container class="bv-example-row">
    <b-row sm='6' offset='3'>
      <b-col>
        <Countdown :counter = 'counter' />
        <div>
          <b-form @submit.prevent="count">
          <b-form-group
          id="input-group-1"
          label="Insert Counter"
          label-for="input-1"
          >
            <b-form-input
            id="input-1"
            v-model="value"
            type="number"
            required
            placeholder="Counter"
            ></b-form-input>
          </b-form-group>

          <b-button type="submit" variant="primary">COUNT!</b-button>
          </b-form>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import Countdown from './components/Countdown.vue'
import Vue from 'vue'
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import BootstrapVue from 'bootstrap-vue'

Vue.use(BootstrapVue)

export default {
  name: 'App',
  components: {
    Countdown
  },
  data() {
    return {
      value: 0,
      counter: 0
    }
  },
  methods: {
    mulai() {
      if(this.counter > 0){
        setTimeout(() => {
          this.counter--
          this.mulai()
        }, 1000)
      }
    },
    count(){
      this.counter = this.value
      this.value = 0
      this.mulai()
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
