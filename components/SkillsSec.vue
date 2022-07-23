<template>
  <section id="skills" class="accent" style="padding: 100px 0">
    <v-container>
      <h3 class="primary--text mb-0 fw-4">Skills</h3>
      <h1 class="white--text">What I Do for Clients</h1>
      <div class="mt-5">
        <!-- <div class="row">
            <div class="col-2">
              <h3 class="fw-4 info--text mb-2 border-bottom">
                Vue
                <v-icon size="14" color="info">mdi-arrow-bottom-right</v-icon>
              </h3>
              <h5 class="fw-4 white--text mb-1">Vue.js</h5>
              <h5 class="fw-4 white--text mb-1">Nuxt.js</h5>
              <h5 class="fw-4 white--text mb-1">Vuetify</h5>
              <h5 class="fw-4 white--text mb-1">BootstrapVue</h5>
              <h5 class="fw-4 white--text mb-1">AntDesign</h5>
              <h5 class="fw-4 white--text mb-1">Quasar</h5>
              <h5 class="fw-4 white--text mb-1">Vuesax</h5>
              <h5 class="fw-4 white--text mb-1">Vuex</h5>
              <h5 class="fw-4 white--text mb-1">Axios</h5>
            </div>
            <div class="col-2">
              <div class="mt-9"></div>
              <h5 class="fw-4 white--text mb-1">Vuelidator</h5>
              <h5 class="fw-4 white--text mb-1">i18n</h5>
              <h5 class="fw-4 white--text mb-1">Javascript</h5>
              <h5 class="fw-4 white--text mb-1">ES6</h5>
              <h5 class="fw-4 white--text mb-1">Advance CSS</h5>
              <h5 class="fw-4 white--text mb-1">CSS Grid</h5>
              <h5 class="fw-4 white--text mb-1">CSS Flexbox</h5>
              <h5 class="fw-4 white--text mb-1">CSS Animation</h5>
            </div>
            <div class="col-2">
              <h3 class="fw-4 info--text mb-2 border-bottom">
                Designing
                <v-icon size="14" color="info">mdi-arrow-bottom-right</v-icon>
              </h3>
              <h5 class="fw-4 white--text mb-1">Adobe Illustrator</h5>
              <h5 class="fw-4 white--text mb-1">Adobe XD</h5>
              <h5 class="fw-4 white--text mb-1">Figma</h5>
              <h5 class="fw-4 white--text mb-1">Canva</h5>
              <h5 class="fw-4 white--text mb-1">UX/UI Designing</h5>
            </div>
            <div class="col-2">
              <h3 class="fw-4 info--text mb-2 border-bottom">
                General
                <v-icon size="14" color="info">mdi-arrow-bottom-right</v-icon>
              </h3>
              <h5 class="fw-4 white--text mb-1">Googling</h5>
              <h5 class="fw-4 white--text mb-1">Problem Solving</h5>
              <h5 class="fw-4 white--text mb-1">Figma</h5>
              <h5 class="fw-4 white--text mb-1">Canva</h5>
            </div>
          </div> -->
        <div>
          <div class="skills-pills">
            <div v-for="(skill, x) in skills" :key="x" class="pill-badge">
              <h4 class="fw-4">{{ skill }}</h4>
            </div>
          </div>
        </div>
      </div>
    </v-container>
  </section>
</template>
<script>
export default {
  data() {
    return {
      skills: [
        'Vue.js',
        'Nuxt.js',
        'React.js',
        'Vuetify',
        'Vuesax',
        'Ant Design',
        'Bootstrap',
        'HTML',
        'CSS',
        'BootstrapVue',
        'CSS Grid',
        'CSS Flexbox',
        'CSS Animations',
        'i18n',
        'Axios',
        'API integration',
        'MDBootstrap',
        'Material Design',
        'Vuelidator',
        'Laravel',
        'Firebase',
        'WordPress',
        'Elementor',
        'WpBackery',
        'Divi',
        'SEO',
        'ACF',
        'SQL',
        'Postgres',
        'UX/UX Desiging',
        'Adobe XD',
        'Adobe Photoshop',
        'Adobe Illustrator',
        'Figma',
        'Sketch',
        'Googling',
        'Speed Optimization',
        'eCommerce',
        'WooCommerce',
        'Online Store',
        'Product Management',
        'Admin Dashboard',
        'Multilingual Website',
        'Bi-directional Website',
        'Admin panel',
        'Pixel Perfect',
        'Responsive',
        'Cross Browser Compatibility',
      ],
    }
  },
}
</script>
<style lang="scss">
.border-bottom {
  position: relative;
  &:after {
    position: absolute;
    width: 30px;
    height: 2px;
    background: $info;
    content: '';
    bottom: 0;
    left: 0;
  }
}

.pill-badge {
  background: $primary-lighten-2;
  padding: 5px 25px;
  border-radius: 50px;
  border: 1px solid $primary;
  transition: all 0.2s ease-in-out;
  cursor: pointer;
  &:hover {
    background: $primary-lighten-1;
  }
}

.skills-pills {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}
</style>
