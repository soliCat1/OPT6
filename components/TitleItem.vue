<template>
  <slot></slot>
</template>

<style lang="scss">
h1 {
  font-size: 41px;
  color: black;
  font-weight: 700;
  margin-bottom: 25px;

  @media (max-width: 1368px) {
    text-align: center;
  }
  
  @media (max-width: 768px) {
    font-size: 30px;
  }
}

h2 {
  font-size: 34px;
  text-align: center;
  margin-bottom: 30px;
  color: black;
  font-weight: 700;

  @media (max-width: 768px) {
    font-size: 24px;
  }
}

h3 {
  color: #1253A2;
  font-size: 31px;
  font-weight: 700;
  margin-bottom: 15px;

  @media (max-width: 768px) {
    font-size: 22px;
    margin-bottom: 10px;
  }
}
</style>