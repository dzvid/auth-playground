<script lang="ts">
import { mapActions, mapState } from 'pinia';
import { defineComponent } from 'vue';
import { useCounterStore } from '@/stores/counter';

export default defineComponent({
  components: { },
  setup() {
    const counterStore = useCounterStore()

    return { counterStore }
  },
  methods: {
    incrementAndPrint() {
      this.counterStore.increment()
      console.log('New Count:', this.counterStore.count)
    },
  },
})

</script>
<template>
  <main>
    {{  counterStore.count  }}
    <button @click="incrementAndPrint">Add</button>
  </main>
</template>
