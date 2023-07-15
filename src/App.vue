<script lang="ts">
import { defineComponent } from 'vue';
import child from './Child.vue';

export default defineComponent({
  components: {
    child,
  },
  computed: {
    child() {
      return 123 // <- this computed property name collides with the component name
    },
  },
})
</script>

<template>
  <!--
    Argument of type '{}' is not assignable to parameter of type '123 & Record<string, unknown>'.
      Type '{}' is not assignable to type '123'.ts(2345)
  -->
  <child />
</template>
