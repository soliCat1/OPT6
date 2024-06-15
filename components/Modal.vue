<template>
  <div v-if="visible" class="modal">
    <div class="modal__content">
      <button class="modal__close" @click="closeWindow">
        <Svg :name="'close'"></Svg>
      </button>
      <iframe
          width="100%"
          height="100%"
          src="https://www.youtube.com/watch?v=8E2AmJl8FZI"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
      ></iframe>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    visible: {
      type: Boolean,
      required: true
    }
  },
  methods: {
    closeWindow() {
      this.$emit('closeModal')
    }
  }
}
</script>

<style scoped>
.modal {
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  z-index: 100;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgb(0,0,0);
  background-color: rgba(0,0,0,0.4);
  border-radius: 15px;
}

.modal__content {
  position: relative;
  background-color: #000000;
  width: 80%;
  height: 80%;
  max-width: 960px;
  height: 532px;
  position: relative;
}

.modal__close {
  cursor: pointer;
  border: none;
  background-color: transparent;
  position: absolute;
  top: -30px;
  right: 0;
  color: #ffffff;

  &:hover {
    color: #1253A2;
  }
}
</style>
