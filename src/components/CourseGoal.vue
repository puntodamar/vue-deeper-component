<template>
  <ul>
    <li v-for="g in goals" :key="g">
      <slot :goal="g"></slot>
    </li>
  </ul>
</template>

<script>
  export default {
    data() {
      return {
        goals: ['Finish the course', 'Learn Vue']
      }
    }
  }
</script>