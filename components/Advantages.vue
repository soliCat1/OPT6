<template>
  <section class="advantages">
    <TitleItem>
      <h2>Плюсы использования сервиса «Компас» для анализа штрафов</h2>
    </TitleItem>
    <ul class="advantages__list">
      <AdvantagesItem v-for="advantage in advantages" :key="advantage.id" :advantage="advantage" />
    </ul>
  </section>
</template>

<script>
export default {
  data: () => ({
    advantages: [
      {
        id: 1,
        img: "carpark",
        title: "Неограниченый автопарк",
        description: "Можно добавить неограниченное кол-во машин и водителей"
      },
      {
        id: 2,
        img: "economy",
        title: "Сокращение затрат до 50%",
        description: "Максимально быстро узнаете о штрафах в автоматическом режиме, тем самым у вас есть время оплатить по скидке"
      },
      {
        id: 3,
        img: "security",
        title: "Безопасность",
        description: "Данные передаются в зашифрованном виде, они доступны только получателю"
      },
      {
        id: 4,
        img: "notification",
        title: "Уведомление о погашении",
        description: "Мы оповестим вас о том, что штраф был погашен и соответствующая запись создана в ГИС ГМП"
      },
      {
        id: 5,
        img: "bill",
        title: "Квитанция об оплате",
        description: "После совершения оплаты банковской картой на Вашу электронную почту придет квитанция об успешной оплате."
      },
      {
        id: 6,
        img: "history",
        title: "Все история сохраняется по каждой машине",
        description: "Вся история штрафов сохраняется по машине и водителю, позволяет анализировать статистику по штрафам"
      }
    ]
  })
}
</script>

<style scoped>
.advantages {
  margin-bottom: 85px;

  @media (max-width: 768px) {
    margin-bottom: 40px;
  }
}
.advantages__list {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 35px;
  list-style: none;

  
  @media (max-width: 1368px) {
    grid-template-columns: repeat(2, 1fr);
    gap: 15px;
  }

  @media (max-width: 768px) {
    display: flex;
    flex-direction: column;
  }
}
</style>

