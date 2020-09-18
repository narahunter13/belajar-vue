<template>
  <b-list-group>
    <b-list-group-item
      v-for="(item,index) in items"
      :key="index"
      class="d-flex justify-content-between align-items-center"
    >
      {{ item }}
      <b-button @click="deleteItem(index)" variant="danger">Selesai</b-button>
    </b-list-group-item>
  </b-list-group>
</template>

<script>
export default {
  name: "List",
  props: {
    items: Array
  },
  methods: {
      deleteItem(index){
          this.items.splice(index, 1)
      }
  }
};
</script>

<style></style>
