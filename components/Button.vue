<template>
  <button :type="$props.type">
    <slot />
  </button>
</template>

<script>
export default {
  props: {
    type: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped lang="scss">
button {
  display: block;
  border-radius: 10px;
  border: none;
  color: #ffffff;
  font-size: 18px;
  font-family: inherit;
  text-align: center;
  background-color: #0584FE;
  cursor: pointer;
  transition: background-color 0.2s ease;

  &:hover {
    background-color: #0372da;
  }

  @media (max-width: 768px) {
    justify-content: center;
    font-size: 16px;
  }
}

.submit {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 10px 20px;
}
.you-tube {
  display: flex;
  align-items: center;
  gap: 5px;
  padding: 10px 20px;
  color: #000000;
  background-color: transparent;
  border: 1px solid #0584FE;

  &:hover {
    background-color: rgba(3, 114, 218, 0.3);
  }
}

.registration {
  font-size: 15px;
  padding: 9px 18px;
}

.documents {
  width: 100%;
  align-items: center;
  padding: 10px 20px;
  margin-top: auto;
}
</style>