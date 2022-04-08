<template>
  <div>
    <input ref="el" type="text" placeholder="Name" v-model="name" />
  </div>
  <div>
    <button @click="submitForm(1, 'test')" :disabled="name.length === 0">
      Submit
    </button>
  </div>
</template>

<script lang="ts">
import { ref, onMounted } from 'vue'
import type { Profile } from './../models/profile.interface'

export default {
  setup() {
    const name = ref('')
    const el = ref()

    const submitForm = (id: number, text: string) => {
      console.log(id, text)
    }

    onMounted(() => {
      el.value.focus()
    })

    return {
      name,
      el,
      submitForm,
    }
  },
}
</script>

<style scoped>
input[type='text'] {
  padding: 5px;
}

button {
  margin-top: 20px;
}
</style>
