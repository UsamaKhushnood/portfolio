<template>
  <section id="testimonials" class="pb-100 pt-16 accent">
    <v-container>
      <h3 class="primary--text mb-0 fw-4">Reviews</h3>
      <h1 class="white--text">What Clients Say About Me</h1>
      <div class="testitmonials mt-16">
        <div class="row">
          <div class="col-3 d-none d-md-flex align-center justify-end">
            <v-btn icon x-large color="primary" @click="showPrev">
              <v-icon>mdi-arrow-left</v-icon>
            </v-btn>
          </div>
          <div class="col-12 col-md-6">
            <VueSlickCarousel v-bind="settings" ref="carousel">
              <div v-for="(review, x) in reviews" :key="x" class="testimonail">
                <h4 class="fw-4">
                  <span>"</span>
                  {{ review.review }}
                  <span>"</span>
                </h4>
                <h3 class="fw-6 text-center primary--text mt-5">
                  {{ review.client }}
                </h3>

                <h6 class="fw-4 text-center">
                  <a
                    class="decoration-none white--text"
                    :href="review.url"
                    target="blank"
                  >
                    {{ review.source }}</a
                  >
                  <v-icon size="14">mdi-arrow-top-right</v-icon>
                </h6>
              </div>
            </VueSlickCarousel>
          </div>
          <div class="col-3 d-none d-md-flex align-center justify-sta4rt">
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
      reviews: [
        {
          review:
            'Sam completed the job quickly and efficiently, and even came back after the contract was complete to help me with a few other things. Will definitely hire again!',
          client: 'Mark McKinney',
          source: 'Upwork',
          url: 'https://www.upwork.com/freelancers/~012416bce059f36249',
        },
        {
          review:
            'He is good in programming. Always available and responsible guy. Will hire again.',
          client: 'Mark McKinney',
          source: 'Upwork',
          url: 'https://www.upwork.com/freelancers/~012416bce059f36249',
        },
        {
          review: 'Well Done Perfect and on Time this guy is Dr. Vue',
          client: 'Zoukar Sulaiman',
          source: 'Upwork',
          url: 'https://www.upwork.com/freelancers/~012416bce059f36249',
        },
        {
          review: 'Well Done on Time and fast and Clean',
          client: 'Zoukar Sulaiman',
          source: 'Upwork',
          url: 'https://www.upwork.com/freelancers/~012416bce059f36249',
        },
        {
          review:
            'Usama did great, he helped me with everything I needed and worked with me until everything was perfect. Thank you.',
          client: 'Ania',
          source: 'Upwork',
          url: 'https://www.upwork.com/freelancers/~012416bce059f36249',
        },
        {
          review:
            'He is experienced developer and enjoyed working with him. Usama has completed his task in a smart way and delivered before deadlines. I really appreciate his work and way of communicating. Thank you Usama. Will keep working together',
          client: 'Summit',
          source: 'Upwork',
          url: 'https://www.upwork.com/freelancers/~012416bce059f36249',
        },
        {
          review:
            'Usama and Rowshan have done a great job! Really liked their proactive attitude, they are always eager to learn and execute fast. We are looking forward to continuously working with them. Best of luck to the Team!! Great job, guys',
          client: 'Rohan',
          source: 'Upwork',
          url: 'https://www.upwork.com/freelancers/~012416bce059f36249',
        },
        {
          review:
            'Good communication, fast response. Serious approach. Gave his personal recommendations while project was in "work in progress" state. He is a very skilled and finished his job as requested.',
          client: 'Daniel',
          source: 'Upwork',
          url: 'https://www.upwork.com/freelancers/~012416bce059f36249',
        },
      ],
      settings: {
        dots: false,
        arrows: false,
        edgeFriction: 0.35,
        speed: 500,
        autoplay: true,
        autoplaySpeed: 2000,
        adaptiveHeight: true,
        infinite: true,
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

.slick-slide > div {
  height: 100% !important;
  margin: 0 5px;
}
</style>
