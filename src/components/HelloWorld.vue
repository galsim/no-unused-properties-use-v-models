<script lang="ts">
import {defineComponent} from 'vue'
import {useVModels} from '@vueuse/core'
export default defineComponent({
  props: {
    msg: {
      type: String,
      required: true
    }
  },
  setup(props,{ emit }) {
    const {
      msg: msgModel
    } = useVModels(props, emit)

    return {
      msgModel
    }
  }
})
</script>

<template>
  <div class="greetings">
    <h1 class="green"></h1>
    <div>
      <input type="text" v-model="msgModel">
    </div>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
