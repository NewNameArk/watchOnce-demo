<!-- <script setup lang="ts">
import { watchOnce  } from '@vueuse/core'
import {ref} from 'vue'

const source = ref(0)

watchOnce(
  source,
  (value) => {
    console.log('变化了', value)
  },
)

const clickedFn = () => {
  source.value ++
}

</script> -->
<script setup lang="ts">
import {ref, watch} from 'vue'

const source = ref(0)
const count = ref(0)

watch(
  source,
  (value) => {
    if (count.value === 0) {
      console.log('变化了', value)
      count.value++
    }
  },
)

const clickedFn = () => {
  source.value ++
}

</script>

<template>
 <div>{{source}}</div>
  <button @click="clickedFn">
    点击按钮
  </button>
</template>