<template>
  <li class="advantage">
    <Svg :name="advantage.img"></Svg>
    <div>
      <span>{{ advantage.title }}</span>
      <p>{{ advantage.description }}</p>
    </div>
  </li>
</template>

<script>
export default {
  props: {
    advantage: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.advantage {
  display: flex;
  gap: 15px;
  background-color: #FBFCFD;
  padding: 24px 20px;
  border-radius: 15px;
  border: 1px solid #EEEFF1;
  align-items: center;
  min-height: 150px;

  
  @media (max-width: 768px) {
    flex-direction: column;
    gap: 30px;
    padding: 20px 10px;
  }
}

.advantage svg {
  flex-shrink: 0;
}

span {
  display: block;
  color: #1253A2;
  font-size: 18px;
  margin-bottom: 10px;
  line-height: 120%;
  font-weight: 700;

  @media (max-width: 768px) {
    text-align: center;
  }
}

p {
  font-size: 15px;
  line-height: 120%;

  @media (max-width: 768px) {
    text-align: center;
  }
}
</style>