<template>
  <div id="app">
    <img alt="Vue logo" src="https://vuejs.org/images/logo.png" />
    {{ value }}
  </div>
</template>

<script lang="ts">
import { Ref, ref, defineComponent } from 'vue';
type test = {
  booleanRef: Ref<Boolean>;
  booleanNoRef: Boolean;
};

export default defineComponent({
  setup() {
    const value: Ref<test> = ref({
      booleanRef: ref(true),
      booleanNoRef: true,
    });

    value.value.booleanRef = ref(false);

    return {
      value,
    };
  },
});
</script>
