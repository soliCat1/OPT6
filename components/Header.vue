<template>
  <header class="header">
    <nav class="header__wrapper">
      <NuxtLink class="header__logo" to="/">
        <Svg :name="'logo'"></Svg>
        <span class="visually-hidden">Ссылка на стартовую страницу</span>
      </NuxtLink>
      <button class="header__button" @click="openMenu" type="button">
      </button>
      <div class="header__container">
        <ul class="header__list">
          <li>
            <NuxtLink to="/tariffs">Тарифы</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/contacts">Контакты</NuxtLink>
          </li>
        </ul>
        <ul class="header__list">
          <li>
            <a class="header__number" href="tel:+74951184422">+7 495 118-44-22</a>
          </li>
          <li>
            <NuxtLink to="/enter">Вход</NuxtLink>
          </li>
          <li>
            <Button type="button" class="registration">
              <NuxtLink class="button" to="/registration">Регистрация</NuxtLink>
            </Button>
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  methods: {
    openMenu(event) {
      event.target.classList.toggle('header__button--active')
    }
  }
}
</script>

<style lang="scss" scoped>
.header {
  background: linear-gradient(to right, rgb(0, 0, 0) 30%, rgb(1, 18, 39, 0.8) 73%);
}

.header__wrapper {
  max-width: 1156px;
  padding: 12px 0;
  display: flex;
  align-items: center;
  margin: 0 auto;

  @media (max-width: 1368px) {
    max-width: 768px;
    padding: 12px 40px;
  }

  @media (max-width: 768px) {
    padding: 12px 20px;
    justify-content: space-between;
    position: relative;
  }
}

.header__list {
  display: flex;
  align-items: center;
  gap: 30px;
  list-style: none;

  @media (max-width: 1368px) {
    gap: 20px;
  }

  @media (max-width: 768px) {
    display: flex;
    flex-direction: column;
    align-items: start;
    gap: 10px;

    &+.header__list {
      margin-top: 10px;
    }
  }
}

.header__container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;

  @media (max-width: 768px) {
    transform: translate3d(200%, 0, 0);
    transition: transform 0.3s ease-in;
    background: linear-gradient(to right, rgb(0, 0, 0) 30%, rgb(1, 18, 39, 0.8) 73%);
    display: block;
    position: absolute;
    top: 50px;
    left: 0;
    padding: 20px;
  }
}

a {
  display: block;
  cursor: pointer;
  text-decoration: none;
  color: #ffffff;
  font-size: 18px;
  transition: color 0.2s ease;
}

a:not(.button):hover {
  color: #0372da;
}

.header__number {
  font-weight: 700;

  @media (max-width: 768px) {
    font-weight: 400;
  }
}

.header__logo {
  margin-right: 30px;

  @media (max-width: 1368px) {
    margin-right: 20px;
  }
}

.header__button {
  flex-shrink: 0;
  border: none;
  display: none;
  cursor: pointer;

  @media (max-width: 768px) {
    display: block;
    position: relative;
    background-color: #ffffff;
    width: 30px;
    height: 3px;
    border-radius: 1px;
    transition: all 0.2s ease;

    &--active {
      background-color: transparent;
    }
  }
}

.header__button::before,
.header__button::after {
  content: '';
  display: block;
  position: absolute;
  background-color: #ffffff;
  left: 0;
  width: 30px;
  height: 3px;
  border-radius: 1px;
  transition: all 0.2s ease;
}

.header__button::before {
  top: 0;
  transform-origin: left top;
  transform: rotate(0deg) translate(0, -8px);
}

.header__button::after {
  bottom: 0;
  transform-origin: right top;
  transform: rotate(0deg) translate(0, 8px);
}

.header__button--active::before {
  transform: translate(6px, -8px) rotate(45deg);
  border-radius: 3px;
}

.header__button--active::after {
  transform: translate(-6px, -8px) rotate(-45deg);
  border-radius: 3px;
}

.header__button--active+.header__container {
  transform: translate3d(0, 0, 0);
}

.header__logo svg {
  display: block;
}
</style>
