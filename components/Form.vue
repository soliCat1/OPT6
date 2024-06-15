<template>
  <form class="form" @submit.prevent="submitForm">
    <div class="form__container">
      <TitleItem>
        <h1>Проверьте штрафы и зарегистрируйтесь в 1 клик</h1>
      </TitleItem>
      <ul class="form__list">
        <li class="form__item">
          <Input :name="'number'">Номер автомобиля</Input>
        </li>
        <li class="form__item">
          <Input :name="'region'">Регион</Input>
        </li>
        <li class="form__item">
          <Input :name="'registration'">Свидетельство о регистрации ТС</Input>
        </li>
      </ul>
      <div class="form__buttons">
        <Button type="submit" class="submit">
          Проверить штрафы
          <Svg :name="'arrow'"></Svg>
        </Button>
        <Button type="button" @click="openModal" class="you-tube">
          <Svg :name="'play'"></Svg>
          О сервисе
          <span>(1 мин. 20 сек)</span>
        </Button>
      </div>
      <p>Нажимая «Проверить штрафы» вы соглашаетесь с политикой обработки персональных данных и принимаете оферту</p>
    </div>
    <img class="form__img" src="/assets/computer.png" width="532" height="335" alt="Изображение ноутбука" />
  </form>
  <Modal @closeModal="closeModal" :visible="modalVisible"/>
</template>

<script>
export default {
  data: () => ({
    modalVisible: false
  }),
  methods: {
    submitForm(event) {
      alert('Ваши данные преданны')
    },
    openModal() {
      this.modalVisible = true
    },
    closeModal() {
      this.modalVisible = false
    }
  }
}
</script>

<style lang="scss" scoped>
.form {
  display: flex;
  gap: 40px;
  margin-bottom: 98px;

  @media (max-width: 1368px) {
    flex-direction: column;
  }

  @media (max-width: 768px) {
    margin-bottom: 50px;
  }
}

.form__container {
  width: 563px;

  @media (max-width: 1368px) {
    width: 100%;
  }
}

.form__list {
  list-style: none;
  display: flex;
  flex-wrap: wrap;
  row-gap: 15px;
  column-gap: 30px;
  margin-bottom: 15px;

  @media (max-width: 1368px) {
    justify-content: space-between;
  }

  @media (max-width: 768px) {
    margin-bottom: 30px;
  }
}

.form__item:nth-child(1) {
  width: 320px;

  @media (max-width: 1368px) {
    width: 60%;
  }

  @media (max-width: 768px) {
    width: 100%;
  }
}

.form__item:nth-child(2) {
  width: 213px;

  @media (max-width: 1368px) {
    width: 35%;
  }

  @media (max-width: 768px) {
    width: 100%;
  }
}

.form__item:nth-child(3) {
  width: 563px;

  @media (max-width: 1368px) {
    width: 100%;
  }
}

.you-tube span {
  color: #1253A2;
}

.form__buttons {
  display: flex;
  gap: 21px;
  margin-bottom: 16px;

  @media (max-width: 768px) {
    flex-direction: column;
  }
}

p {
  font-size: 13px;
  color: #8F8F8F;
}

.form__img {
  @media (max-width: 1368px) {
    display: block;
    margin: 0 auto;
  }

  @media (max-width: 768px) {
    width: 100%;
    height: auto;
  }
}
</style>
