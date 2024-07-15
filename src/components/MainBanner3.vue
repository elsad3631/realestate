<template>
  <div class="slidearea ps-0">
    <div class="silder-three">
      <Swiper
        class="swiper-container main-silder-swiper-03"
        :modules="module"
        :speed="1500"
        :loop="true"
        :parallax="true"
        :pagination="pagination"
        :navigation="{
          prevEl: '.btn-prev',
          nextEl: '.btn-next'
        }"
        :autoplay="{ delay: 1500 }"
      >
        <SwiperSlide class="swiper-slide" v-for="({ img }, ind) in mainSlider" :key="ind">
          <div class="silder-content" data-swiper-parallax="-40%">
            <div class="container">
              <div class="inner-content row align-items-center g-0">
                <div class="col-md-6">
                  <div class="inner-text">
                    <h6 class="text text-primary">Cosa facciamo?</h6>
                    <h4 class="title">
                      Acquisizione e distribuzione dei dati  <br />
                      nell'ambito di organizzazioni SIT
                    </h4>
                    <p>
                      Operiamo tramite sistemi informativi computerizzati (GIS) con acquisizione, registrazione, analisi, per visualizzazione e restituzione di informazioni derivanti da dati geografici (geo-riferiti). Mappature con droni, telecamere 360°, misurazioni GPS. 
                    </p>
                    <div>
                      <RouterLink
                        to="/services"
                        class="btn btn-primary btn-rounded btn-md hover-icon"
                      >
                        <span>Scopri di più</span>
                        <i class="fas fa-arrow-right"></i>
                      </RouterLink>
                      <RouterLink
                        to="/services"
                        class="btn btn-primary btn-rounded m-l15 btn-border btn-md hover-icon"
                      >
                        <span>I nostri servizi</span>
                        <i class="fas fa-arrow-right"></i>
                      </RouterLink>
                    </div>
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="overlay-slide" data-swiper-parallax="100%">
                    <img :src="img" alt="" />
                  </div>
                </div>
              </div>
            </div>
          </div>
        </SwiperSlide>
        <div class="swiper-pagination style-2"></div>
        <div class="slider-three-pagination">
          <div class="btn-prev swiper-button-prev3 swiper-button-white">
            <i class="las la-angle-left"></i>
          </div>
          <div class="btn-next swiper-button-next3 swiper-button-white">
            <i class="las la-angle-right"></i>
          </div>
        </div>
      </Swiper>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Navigation, Pagination, Autoplay, Parallax } from 'swiper/modules'
import slide_pic1 from '@/assets/images/main-slider/slider3/pic1.jpg'
import slide_pic2 from '@/assets/images/main-slider/slider3/pic2.jpg'
import slide_pic3 from '@/assets/images/main-slider/slider3/pic3.jpg'

export default defineComponent({
  components: { Swiper, SwiperSlide },
  setup() {
    return {
      mainSlider: [{ img: slide_pic1 }, { img: slide_pic2 }, { img: slide_pic3 }],
      module: [Navigation, Pagination, Autoplay, Parallax],
      pagination: {
        el: '.swiper-pagination',
        clickable: true,
        renderBullet: function (index: number, className: string) {
          return '<span class="' + className + '">' + '0' + (index + 1) + '</span>'
        }
      }
    }
  }
})
</script>

<style scoped></style>
