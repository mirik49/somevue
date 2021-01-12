<template>
  <ul @click="() => validate()"
    ref="child"
  >
    <li>
      <button>One component {{ index }}</button>
    </li>
    <slot></slot>
  </ul>
</template>

<script>

export default {
  name: "comp",
  props: ['index'],
  methods: {
    validate() {
      console.log("validate" + this.index);
      // console.log(this.$root.$children);
      console.log(this.$refs.child);
      // this.$children.validate();
    }
  },
  // mounted() {
  //
  // },
  // created: function() {
  //   this.$parent.$on('update', this.validate);
  // }
};
</script>
