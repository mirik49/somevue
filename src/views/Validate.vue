<template>
  <div>

    <ul v-for="(item, key) in items">
      <li @click="() => validate()">One component, {{item.name}}{{key}}</li>
      <validate
        v-if="item.children && item.children.length"
            :items="item.children"
      >
      </validate>
    </ul>
  </div>
</template>

<script>
import {mapGetters} from "vuex";

export default {
  name: "validate",
  props: ['items', 'dat', 'item'],
  data() {
    return {

    }
  },
  mounted() {
  },
  methods: {
    validate() {
      console.log("validate")
    }
  },
  beforeCreate: function(){
    this.$options.components.Home = require("./Home.vue").default;
  }
};
</script>
