<template>
  <div>
    <section class="hero-section d-flex align-center">
      <v-container class="position-relative">
        <v-row align="center">
          <v-col cols="6">
            <h3 class="primary--text mb-0 fw-6">Usama Khushnood</h3>
            <h1 class="hero-text mb-10">Expert Vuejs Developer.</h1>
            <div class="mb-10">
              <ul>
                <li class="mb-1">
                  <h3 class="fw-4">Web Development</h3>
                </li>
                <li class="mb-1">
                  <h3 class="fw-4">Digital Marketing</h3>
                </li>
                <li class="mb-1">
                  <h3 class="fw-4">Graphic Design</h3>
                </li>
              </ul>
            </div>
            <v-row>
              <v-col cols="4">
                <div class="d-flex align-center">
                  <h1 class="hero-text">3+</h1>
                  <h4 class="fw-4 info--text ml-3">
                    Years of <br />
                    Experience
                  </h4>
                </div>
              </v-col>
              <v-col cols="6">
                <div class="d-flex align-center">
                  <h1 class="hero-text">50+</h1>
                  <h4 class="fw-4 info--text ml-3">
                    Happy <br />
                    Customers
                  </h4>
                </div>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="6" class="d-flex justify-center">
            <div class="hero-img-wrapper">
              <div class="vector-background"></div>
              <v-img
                src="/images/dp2.jpg"
                class="dp"
                width="320"
                height="450"
                position="left top"
              ></v-img>
            </div>
          </v-col>
        </v-row>
        <a class="decoration-none levitating-arrow" href="#work">
          <v-icon color="#fff" size="50px"> mdi-arrow-down </v-icon>
        </a>
      </v-container>
    </section>
    <section id="work" class="secondary d-flex align-center">
      <v-container>
        <v-row align="center">
          <v-col cols="12">
            <h3 class="primary--text mb-0 fw-4">Work</h3>
            <div class="d-flex justify-space-between align-center mb-10">
              <h1 class="">Past Projects</h1>
              <div>
                <v-btn text tile class="text-capitalize"> ALL </v-btn>
                <v-btn text tile class="text-capitalize"> Vuejs </v-btn>
                <v-btn text tile class="text-capitalize"> Nuxtjs </v-btn>
                <v-btn text tile class="text-capitalize"> WordPress </v-btn>
                <v-btn text tile class="text-capitalize"> NFTs </v-btn>
              </div>
            </div>
          </v-col>
          <v-col cols="12">
            <div class="position-relative">
              <VueSlickCarousel ref="carousel" class="row" v-bind="settings">
                <div v-for="x in 4" :key="x" class="recent-project col-12">
                  <v-img
                    :src="`/images/recent/nft${x}.png`"
                    class="dp pa-5"
                    height="550"
                  >
                    <a
                      href="#"
                      class="secondary info-panel pa-10 h-100 flex-column justify-space-between"
                    >
                      <!-- <div> -->
                      <v-icon size="45">mdi-arrow-top-right</v-icon>
                      <div class="project-details">
                        <h3 class="fw-6 white--text">Project Name</h3>
                        <h5 class="fw-4 info--text">Open Website</h5>
                      </div>
                      <!-- </div> -->
                    </a>
                  </v-img>
                </div>
              </VueSlickCarousel>
              <div class="controller mt-6 d-flex justify-end">
                <v-btn color="#fff" icon class="mr-2" @click="showPrev">
                  <v-icon>mdi-arrow-left</v-icon>
                </v-btn>
                <v-btn color="#fff" icon @click="showNext">
                  <v-icon>mdi-arrow-right</v-icon>
                </v-btn>
              </div>
            </div>
          </v-col>
        </v-row>
      </v-container>
    </section>
    <section id="skills" class="accent d-flex align-center">
      <v-container></v-container>
    </section>
  </div>
</template>

<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
export default {
  name: 'IndexPage',
  components: { VueSlickCarousel },
  data() {
    return {
      settings: {
        dots: false,
        arrows: false,
        focusOnSelect: true,
        infinite: true,
        speed: 500,
        slidesToShow: 3,
        slidesToScroll: 1,
        touchThreshold: 5,
      },
    }
  },
  methods: {
    showNext() {
      this.$refs.carousel.next()
    },
    showPrev() {
      this.$refs.carousel.prev()
    },
  },
}
</script>
<style lang="scss">
section {
  height: calc(100vh - 70px);
  min-height: 700px;
}

.hero-text {
  font-size: 45px;
}

.vector-background {
  height: 450px;
  width: 320px;
  background: #f54212;
  border-radius: 10px;
  transition: all 0.2s ease-in-out;
}

.hero-img-wrapper {
  position: relative;
  .vector-background {
    height: 450px;
    width: 320px;
    background: #f54212;
    border-radius: 10px;
    transform: rotate(355deg);
    transition: all 0.2s ease-in-out;
  }
  .v-image.dp {
    position: absolute;
    top: 0;
    border-radius: 10px;
    transform: rotate(5deg);
    left: 80px;
    transition: all 0.2s ease-in-out;
  }

  &:hover {
    cursor: pointer;
    .vector-background {
      transform: rotate(356deg);
    }
    .v-image.dp {
      transform: rotate(4deg);
    }
  }
}
.levitating-arrow {
  position: absolute;
  // margin-top: 100px;
  animation: levitating 2s ease infinite;
}

@keyframes levitating {
  0% {
    transform: translateY(0);
  }

  30% {
    transform: translateY(20px);
  }
}

.recent-project {
  cursor: pointer;
  .v-image,
  .info-panel {
    border-radius: 10px;
  }
  .info-panel {
    display: flex;
    text-decoration: none;
    opacity: 0;
    transition: all 0.2s ease-in-out;
  }
  &:hover {
    .info-panel {
      opacity: 0.9;
    }
  }
}
</style>
