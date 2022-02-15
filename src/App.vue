<template>
  <div class="carouselComponent">
    <Carousel class="caro" :autoplay="2000" :wrap-around="true">
      <Slide v-for="image in images" :key="image.id">
        <!-- <div class="carousel__item carouselImgContainer">
        <img class="image" src="./assets/1.svg" alt="" />
        <div class="lol">loooll</div>
      </div> -->

        <div class="carousel__item">
          <img class="image" :src="image.url" alt="" />
          <!-- {{ image.id }} -->
          <div class="carouselTexts">{{ image.message }}</div>
        </div>
      </Slide>

      <template class="ads" #addons>
        <Pagination class="pags" />
      </template>
    </Carousel>
  </div>
</template>

<script scoped>
import image1 from "./assets/1.svg";
import image2 from "./assets/2.svg";
import image3 from "./assets/3.svg";
import { defineComponent } from "vue";
import { Carousel, Pagination, Slide } from "vue3-carousel";

import "vue3-carousel/dist/carousel.css";

export default defineComponent({
  name: "Autoplay",
  components: {
    Carousel,
    Slide,
    Pagination,
  },
  data() {
    return {
      images: [
        { id: 1, url: image1, message: "Hızlıca randevu alın ve düzenleyin" },
        {
          id: 2,
          url: image2,
          message: "Dilediğiniz yerden doktorunuzla görüntülü görüşün",
        },
        {
          id: 2,
          url: image3,
          message: "Test sonuçlarınızı ve raporlarınızı anında görüntüleyin",
        },
      ],
    };
  },
});
</script>
<style>
.carouselComponent {
  overflow: hidden;
  width: 500px;
  height: 457px;
  display: flex;
  border: 10px solid gold;

  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.caro {
  display: flex;
  /* border: 10px solid gold; */

  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.pags {
  width: 100%;
  position: relative;
  right: 1.5rem;
}
.carousel__pagination-button {
  margin: var(--vc-pgn-margin);
  width: var(--vc-pgn-width);
  height: var(--vc-pgn-height);
  border-radius: var(--vc-pgn-height);
  border: 0;
  cursor: pointer;
  background-color: black;
}

.carousel__pagination-button--active {
  background-color: black;
}
.carouselImgContainer {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.image {
  width: 400px;
  height: 400px;
}
.carouselTexts {
  width: auto;
  font-family: Nunito Sans;
  font-style: normal;
  font-weight: 800;
  font-size: 20px;
  line-height: 130%;
  /* or 26px */

  text-align: center;
  letter-spacing: -0.01em;

  /* Primary */

  color: #3c4e69;
}
</style>
