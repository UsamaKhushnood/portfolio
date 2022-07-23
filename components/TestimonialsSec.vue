<template>
  <section id="testimonials" class="pb-100 pt-16 accent">
    <v-container>
      <h3 class="primary--text mb-0 fw-4">Reviews</h3>
      <h1 class="white--text">What Clients Say About Me</h1>
      <div class="testitmonials mt-16">
        <div class="row">
          <div class="col-3 d-flex align-center justify-end">
            <v-btn icon x-large color="primary" @click="showPrev">
              <v-icon>mdi-arrow-left</v-icon>
            </v-btn>
          </div>
          <div class="col-6">
            <VueSlickCarousel v-bind="settings" ref="carousel">
              <div v-for="x in 5" :key="x" class="testimonail">
                <h4 class="fw-4">
                  <span>"</span>
                  Lorem ipsum dolor sit amet consectetur adipisicing elit. Eaque
                  voluptate laudantium accusamus laboriosam, minus quasi omnis
                  aut recusandae vero. Non omnis at libero iste similique
                  inventore suscipit iure enim.
                  <span>"</span>
                </h4>
                <h3 class="fw-6 text-center primary--text mt-5">
                  Client's Name
                </h3>

                <h6 class="fw-4 text-center">
                  <a
                    class="decoration-none white--text"
                    href="https://www.upwork.com/freelancers/usamakhushnood2"
                    target="blank"
                  >
                    Upwork</a
                  >
                  <v-icon size="14">mdi-arrow-top-right</v-icon>
                </h6>
              </div>
            </VueSlickCarousel>
          </div>
          <div class="col-3 d-flex align-center justify-sta4rt">
            <v-btn icon x-large color="primary" @click="showNext">
              <v-icon>mdi-arrow-right</v-icon>
            </v-btn>
          </div>
        </div>
      </div>
    </v-container>
  </section>
</template>
<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
export default {
  name: 'TestimonialsSection',
  components: { VueSlickCarousel },
  data() {
    return {
      settings: {
        dots: false,
        arrows: false,
        edgeFriction: 0.35,
        infinite: true,
        speed: 500,
        slidesToShow: 1,
        slidesToScroll: 1,
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
.testimonail {
  display: flex !important;
  flex-direction: column;
  //   width: 700px !important;
  margin: 0 auto;
  text-align: center;
  padding: 26px;
  border-radius: 10px;
  background: $primary-lighten-2;
}
</style>
