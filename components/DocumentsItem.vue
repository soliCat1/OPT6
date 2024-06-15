<template>
  <div class="swiper__slide">
    <TitleItem><h3>{{ document.title }}</h3></TitleItem>
    <p>{{ document.description }}</p>
    <Button :type="'button'" class="documents">Перейти</Button>
  </div>
</template>

<script>
export default {
  props: {
    document: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.swiper__slide {
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  padding: 25px;
  border-radius: 15px;
  min-height: 450px;
  width: 100%;
  display: flex;
  flex-direction: column;

  @media (max-width: 768px) {
    padding: 15px;
    min-height: 300px;
  }
}

p {
  font-size: 18px;

  @media (max-width: 768px) {
    font-size: 15px;
  }
}
</style>