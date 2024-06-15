<template>
  <div>
    <Header />
    <div class="container">
      <slot />
    </div>
  </div>
</template>

<style>
.container {
  max-width: 1156px;
  margin: 0 auto;
  padding: 80px 0 200px 0;

  @media (max-width: 1368px) {
    max-width: 768px;
    padding: 80px 40px 100px 40px;
  }

  @media (max-width: 768px) {
    max-width: 768px;
    padding: 40px 20px;
  }
}
</style>