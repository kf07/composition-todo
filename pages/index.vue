<template>
  <div class="container">
    <div>
      <div>{{ state.count }}</div>
      <div>{{ doubleCount }}</div>
      <button @click="add">プラス</button>
      <button @click="minus">マイナス</button>
    </div>
  </div>
</template>

<script lang="ts">
import { createComponent, reactive, computed } from '@vue/composition-api'
export default createComponent({
  setup() {
    const state = reactive({
      count: 0
    })
    const doubleCount = computed(() => state.count * 2)
    const add = () => {
      state.count += 1
    }
    const minus = () => {
      state.count -= 1
    }
    return {
      state,
      doubleCount,
      add,
      minus
    }
  }
})
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
