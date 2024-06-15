<template>
  <div>
    <label :for="name">
      <slot />
    </label>
    <input :id="name" :name="name" required>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped lang="scss">
div {
  display: flex;
  flex-direction: column;
  width: 100%;
}

label {
  margin-bottom: 5px;
  font-size: 12px;
}

input {
  padding: 10px;
  border-radius: 5px;
  border: 1px solid #ccc;

  &:focus-visible {
    outline: 1px solid #1253A2;
  }
}
</style>