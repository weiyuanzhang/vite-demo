<template>
  <el-menu-item :index="index">
    <i v-if="icon" :class="[ icon.includes('fa')? 'fas' : '', icon ]"/>
    <template #title>{{ title }}</template>
  </el-menu-item>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'Item',
  props: {
    title: String,
    icon: String,
    index: String
  },
  setup(props) {
    let classObj
    const { icon } = props
    if (icon.includes("fa")) {
      classObj = ["fas", icon]
    }
    return {
      classObj
    }
  }
})
</script>
