<template>
  <section id="home" class="hero-section full-height d-flex align-center">
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
        <img src="/icons/arrow-down.png" />
        <!-- <v-icon color="#fff" size="50px"> mdi-arrow-down </v-icon> -->
      </a>
    </v-container>
  </section>
</template>
<style lang="scss">
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
</style>
