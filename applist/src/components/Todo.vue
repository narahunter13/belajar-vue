<template>
  <div id="app">
    <b-jumbotron header="TODO LIST APP" lead="Aplikasi Sederhana Vue js">
      <div>
        <b-form @submit.prevent="sendToParent()">
          <b-form-group id="input-group-2">
            <b-form-input id="input-2" v-model="item" required placeholder="Do something?"></b-form-input>
          </b-form-group>
          <b-button type="submit" variant="primary">Add</b-button>
        </b-form>
      </div>
    </b-jumbotron>
  </div>
</template>

<script>
export default {
  name: "Todo",
  data() {
    return {
      item: ""
    };
  },
  methods: {
    sendToParent: function() {
      this.$emit("childData", this.item);
      this.item = "";
    }
  }
};
</script>

<style>
#app {
  text-align: center;
}
</style>
