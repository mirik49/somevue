<template>
  <div>
    <comp :index="1">
      <comp :index="2"></comp>
      <comp :index="3">
        <comp :index="4"></comp>
      </comp>
      <comp :index="5"></comp>
    </comp>

  </div>
</template>

<script>
import {mapGetters} from "vuex";
import Validate from "@/views/Validate";
import Comp from "@/views/Comp";

export default {
  name: "home",
  components: {Validate, Comp},
  beforeCreate: function () {
    this.$options.components.Home = require("./Home.vue").default;
  }
};
</script>
