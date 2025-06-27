<template>
  <div>
    <h2>Manage Goal</h2>
    <input type="text" ref="goal">
    <button @click="setGoal">Set Goal</button>
    <teleport to="#app">
      <error-alert v-if="inputIsInvalid">
        <h2>Input is invalid</h2>
        <p>Please input a valid input</p>
        <button @click="confirmError">Okey</button>
      </error-alert>
    </teleport>

  </div>
</template>

<script>
  import ErrorAlert from "@/components/ErrorAlert.vue";

  export default {
    components: {ErrorAlert},
    data() {
      return {
        inputIsInvalid: false,
      }
    },
    methods: {
      setGoal() {
        const value = this.$refs.goal.value;
        if (value === '') {
          this.inputIsInvalid = true;
        }
      },
      confirmError() {
        this.inputIsInvalid = false;
      }
    }
  }
</script>