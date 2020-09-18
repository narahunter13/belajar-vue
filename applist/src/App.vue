<template>
  <b-container class="bv-example-row">
    <b-row cols="8" offset="4">
      <b-col>
        <Todo @childData="getChildData" />
        <List :items="items" />
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import Vue from "vue";
import BootstrapVue from "bootstrap-vue";
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";

import Todo from "./components/Todo.vue";
import List from "./components/List.vue";

// Install BootstrapVue
Vue.use(BootstrapVue);

export default {
  name: "App",
  components: {
    Todo,
    List
  },
  data() {
    return {
      items: []
    };
  },
  methods: {
    getChildData: function(params) {
      this.items.push(params);
    }
  }
};
</script>

<style></style>
