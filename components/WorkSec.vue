<template>
  <section id="work" class="secondary py-16 full-height d-flex align-center">
    <v-container>
      <v-row align="center">
        <v-col cols="12">
          <h3 class="primary--text mb-0 fw-4">Work</h3>
          <div class="d-flex justify-space-between align-center mb-10">
            <h1 class="">Past Projects</h1>
            <!-- <div>
              <v-btn text tile class="text-capitalize"> ALL </v-btn>
              <v-btn text tile class="text-capitalize"> Vuejs </v-btn>
              <v-btn text tile class="text-capitalize"> Nuxtjs </v-btn>
              <v-btn text tile class="text-capitalize"> WordPress </v-btn>
              <v-btn text tile class="text-capitalize"> NFTs </v-btn>
            </div> -->
          </div>
        </v-col>
        <v-col cols="12">
          <div class="position-relative">
            <VueSlickCarousel ref="carousel" class="row" v-bind="settings">
              <div
                v-for="(project, x) in projects"
                :key="x"
                class="recent-project col-12 position-relative"
              >
                <v-img
                  :src="`/images/projects/${project.cover}`"
                  class="dp pa-5"
                  height="450"
                  cover
                >
                  <div
                    v-if="project.cover == null"
                    class="d-flex no-dp-panel flex-column align-center h-100 justify-center"
                  >
                    <img
                      class="projectLogo"
                      :src="`/images/projects/${project.logo}`"
                      width="100px"
                    />
                    <div class="mt-5">
                      <h6 class="fw-4">Click to View</h6>
                    </div>
                  </div>

                  <a
                    :href="project.url"
                    target="blank"
                    class="secondary info-panel pa-10 h-100 flex-column justify-space-between"
                  >
                    <!-- <div> -->
                    <v-icon size="45">mdi-arrow-top-right</v-icon>
                    <div class="project-details">
                      <h3 class="fw-6 white--text">{{ project.title }}</h3>
                      <div class="d-flex py-1">
                        <h6
                          v-for="(stack, i) in project.stack"
                          :key="i"
                          class="fw-4 white--text mr-2 skill-badge"
                        >
                          {{ stack }}
                        </h6>
                      </div>
                      <h5 class="fw-4 info--text">Click to Open Website</h5>
                    </div>
                    <!-- </div> -->
                  </a>
                </v-img>
              </div>
            </VueSlickCarousel>
            <div class="controller d-flex justify-end mt-6">
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
</template>
<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
export default {
  name: 'WorkSection',
  components: { VueSlickCarousel },
  data() {
    return {
      projects: [
        {
          title: 'Cy-B3lla',
          url: 'https://cy-b3lle.netlify.app/',
          logo: null,
          cover: 'nft1.png',
          type: 'Website',
          stack: ['Vue', 'Nuxt', 'NFT'],
        },

        {
          title: 'AngeliCamanzo',
          url: 'https://angelicamanzo.com/',
          logo: null,
          cover: 'angelica.jpg',
          type: 'Website',
          stack: ['Wordpress', 'Divi', 'Custom Design'],
        },
        {
          title: 'UncorkedCommerce',
          url: 'http://uncorkedcommerce.com/',
          logo: null,
          cover: 'uncorked.png',
          type: 'Website',
          stack: ['Wordpress'],
        },
        {
          title: 'Mandelli',
          url: 'https://mandelli.it/',
          logo: null,
          cover: 'mandelli.jpg',
          type: 'Website',
          stack: ['Wordpress'],
        },
        {
          title: 'SwopnoBazar',
          url: 'https://swopnobazar.com',
          logo: 'swopnobazar.png',
          cover: null,
          type: 'Website',
          stack: ['Wordpress'],
        },
        {
          title: 'W-Shop',
          url: 'https://w-shop.co/',
          logo: 'wshop.png',
          cover: null,
          type: 'Website',
          stack: ['Wordpress'],
        },

        {
          title: 'Braap',
          url: 'https://braap.io',
          logo: null,
          cover: 'braap.png',
          type: 'Website',
          stack: ['Vue', 'Nuxt'],
        },
      ],
      settings: {
        dots: false,
        arrows: false,
        focusOnSelect: true,
        infinite: true,
        speed: 500,
        slidesToShow: 3,
        slidesToScroll: 1,
        touchThreshold: 5,
        autoplay: true,
        autoplaySpeed: 5000,
        responsive: [
          {
            breakpoint: 560,
            settings: {
              slidesToShow: 1,
              slidesToScroll: 1,
              infinite: true,
            },
          },
        ],
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
.dp {
  background-color: $accent;
}
.recent-project {
  cursor: pointer;
  .v-image,
  .info-panel {
    border-radius: 10px;
  }
  .v-image,
  .v-image__image {
    box-shadow: inset 1px 1px 12px 4px black;
    border: 1px solid #000;
  }
  .info-panel {
    display: flex;
    text-decoration: none;
    opacity: 0;
    transition: all 0.2s ease-in-out;
    position: absolute;
    width: calc(100% - 20px);
    height: calc(100% - 20px) !important;
    top: 10px;
    left: 10px;
  }
  &:hover {
    .info-panel {
      opacity: 1;
    }
  }
}

.v-responsive__sizer {
  padding: 0 !important;
}

.skill-badge {
  background: #575757a8;
  padding: 1px 10px;
  border-radius: 50px;
  border: 1px solid #ffffff45;
}
</style>
