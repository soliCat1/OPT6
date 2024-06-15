<template>
  <section>
    <TitleItem>
      <h2 style="margin: 0">Документы</h2>
    </TitleItem>
    <Swiper :modules="modules" :breakpoints="{
      320: {
        slidesPerView: 1,
        slidesPerGroup: 1,
        spaceBetween: 35
      },
      768: {
        slidesPerView: 2,
        slidesPerGroup: 2,
        spaceBetween: 35
      },
      1368: {
        slidesPerView: 3,
        slidesPerGroup: 3,
        spaceBetween: 35
      }
    }" :navigation="{
  nextEl: '.swiper-button-next',
  prevEl: '.swiper-button-prev',
}" :pagination="{
  el: '.swiper-pagination',
  clickable: true
}" class="swiper">
      <SwiperSlide v-for="document in documents" :key="document.id">
        <DocumentsItem :document="document" />
      </SwiperSlide>
      <div class="swiper-pagination">
      </div>
      <div class="swiper-button-next">
      </div>
      <div class="swiper-button-prev">
      </div>
    </Swiper>
  </section>
</template>

<script>
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';
import { Navigation, Pagination } from 'swiper/modules';

export default {
  data: () => ({
    documents: [
      {
        id: 1,
        title: "Лицензионный договор",
        description: "Механизм разбрасывания веерного типа приводится в действие от колес тележки, отличается простой и надежной конструкцией, не нуждается в смазке."
      },
      {
        id: 2,
        title: "Политика обработки персональных данных",
        description: "Радиус разброса ПГМ составляет до 3 метров и может регулироваться."
      },
      {
        id: 3,
        title: "Информация об оплате",
        description: "Десятипозиционный переключатель дозировки расположен на ручке тележки и позволяет очень точно регулировать объем рассыпаемого реагента с учетом его массы и фракции."
      },
      {
        id: 4,
        title: "Лицензионный договор",
        description: "Механизм разбрасывания веерного типа приводится в действие от колес тележки, отличается простой и надежной конструкцией, не нуждается в смазке."
      },
      {
        id: 5,
        title: "Политика обработки персональных данных",
        description: "Радиус разброса ПГМ составляет до 3 метров и может регулироваться."
      },
      {
        id: 6,
        title: "Информация об оплате",
        description: "Десятипозиционный переключатель дозировки расположен на ручке тележки и позволяет очень точно регулировать объем рассыпаемого реагента с учетом его массы и фракции."
      }
    ]
  }),
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Navigation, Pagination]
    }
  }
}
</script>

<style lang="scss">
.swiper-button-next,
.swiper-button-prev {
  background-color: rgba(166, 183, 212, 0.47);
  color: #ffffff;
  width: 40px;
  height: 80px;
  transition: background-color 0.2s ease;

  @media (max-width: 768px) {
    width: 30px;
    height: 60px;
  }

  &:hover {
    background-color: rgba(3, 114, 218, 0.47);
  }
}

.swiper-button-next::after {
  font-size: 28px;
  margin-left: 10px;
  
  @media (max-width: 768px) {
    font-size: 24px;
  }
}

.swiper-button-prev::after {
  font-size: 28px;
  margin-right: 10px;

  @media (max-width: 768px) {
    font-size: 24px;
  }
}

.swiper-button-next {
  border-bottom-left-radius: 100px;
  border-top-left-radius: 100px;
}

.swiper-button-prev {
  border-bottom-right-radius: 100px;
  border-top-right-radius: 100px;
}

.swiper {
  padding: 40px 27px;
}

.swiper-pagination-bullet {
  width: 7px;
  height: 7px;
  position: relative;

  &-active::after {
    content: '';
    width: 10px;
    height: 10px;
    background-color: #007AFF;
    border-radius: 50%;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translateX(-50%) translateY(-50%);
  }
}

.swiper-pagination-bullets.swiper-pagination-horizontal {
  bottom: 0;
}
</style>

