<template>
  <section id="contact" class="pt-16 pb-100">
    <v-overlay :value="overlay">
      <v-progress-circular indeterminate size="64"></v-progress-circular>
    </v-overlay>
    <v-snackbar v-model="snackbar" vertical top right>
      {{ text }}

      <template #action="{ attrs }">
        <v-btn color="primary" text v-bind="attrs" @click="snackbar = false">
          Close
        </v-btn>
      </template>
    </v-snackbar>
    <v-container>
      <h3 class="primary--text mb-0 fw-4">Contact</h3>
      <h1 class="white--text">Looking forward to hear from you.</h1>
      <div class="row mt-md-16 mt-5 flex-column-reverse flex-md-row">
        <div class="col-md-6 col-12 mt-md-0 mt-5">
          <div class="social-media-links">
            <a
              href="mailto:usamakhushnood4@gmail.com"
              class="social-link decoration-none white--text d-flex align-center py-3"
              target="blank"
            >
              <v-icon>mdi-email</v-icon>
              <span class="ml-2">Send Me an Email</span>
            </a>
            <a
              href="tel:+923314278863"
              class="social-link decoration-none white--text d-flex align-center py-3"
              target="blank"
            >
              <v-icon>mdi-phone</v-icon>
              <span class="ml-2"> Call Me </span>
            </a>
            <a
              href="http://meet.google.com/"
              class="social-link decoration-none white--text d-flex align-center py-3"
              target="blank"
            >
              <v-icon>mdi-laptop-account</v-icon>
              <span class="ml-2"> Schedule a Meeting </span>
            </a>
            <a
              href="skype:live:usamakhushnood"
              class="social-link decoration-none white--text d-flex align-center py-3"
              target="blank"
            >
              <v-icon>mdi-skype</v-icon>
              <span class="ml-2"> Add Me on Skype </span>
            </a>
            <a
              href="https://wa.me/+923314278863"
              class="social-link decoration-none white--text d-flex align-center py-3"
              target="blank"
            >
              <v-icon>mdi-whatsapp</v-icon>
              <span class="ml-2"> Whatsapp </span>
            </a>
          </div>
        </div>
        <div class="col-md-6 col-12 position-relative">
          <form ref="form" @submit.prevent="sendEmail">
            <div class="row">
              <div class="col-12 pb-0 col-md-6">
                <v-text-field
                  v-model="form.name"
                  :rules="requiredRule"
                  color="white"
                  label="Name"
                  name="user_name"
                  dense
                  outlined
                  required
                ></v-text-field>
              </div>
              <div class="col-12 pb-0 col-md-6">
                <v-text-field
                  v-model="form.email"
                  :rules="emailRules"
                  color="white"
                  label="Email"
                  name="user_email"
                  dense
                  outlined
                  required
                ></v-text-field>
              </div>
              <!-- <div class="col-12">
                <v-text-field
                  color="white"
                  label="Phone Number"
                  dense
                  outlined
                  hide-details
                ></v-text-field>
              </div> -->
              <!-- <div class="col-12 col-md-6">
                <v-text-field
                  color="white"
                  label="Subject"
                  dense
                  outlined
                  hide-details
                ></v-text-field>
              </div> -->
              <div class="col-12 pt-0">
                <v-textarea
                  v-model="form.message"
                  color="white"
                  :rules="requiredRule"
                  label="Message"
                  name="message"
                  dense
                  outlined
                  required
                ></v-textarea>
              </div>
              <div class="col-12 d-flex">
                <v-btn color="primary" class="ml-auto" type="submit"
                  >Send <v-icon size="15" class="ml-5">mdi-send</v-icon>
                </v-btn>
              </div>
            </div>
          </form>
        </div>
      </div>
    </v-container>
  </section>
</template>
<script>
import emailjs from '@emailjs/browser'
export default {
  data() {
    return {
      snackbar: false,
      overlay: false,
      text: '',
      form: {
        name: null,
        email: null,
        message: null,
      },
      requiredRule: [(v) => !!v || 'Field is required'],
      emailRules: [
        (v) => !!v || 'E-mail is required',
        (v) =>
          /^(([^<>()[\]\\.,;:\s@']+(\.[^<>()\\[\]\\.,;:\s@']+)*)|('.+'))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/.test(
            v
          ) || 'E-mail must be valid',
      ],
    }
  },
  methods: {
    sendEmail() {
      this.overlay = true
      // eslint-disable-next-line import/no-named-as-default-member
      emailjs
        .sendForm(
          'service_tjsv2du',
          'template_cm73l2d',
          this.$refs.form,
          'd281BhHn7WJH6Xdkk'
        )
        .then(
          () => {
            this.form = {
              name: null,
              email: null,
              message: null,
            }
            this.text =
              'Thank for very much for sending message, I will reach to you soon!'
            this.snackbar = true
            this.overlay = false
          },
          () => {
            this.text = 'Servcie not Working'
            this.snackbar = true
            this.overlay = false
          }
        )
    },
  },
}
</script>
<style lang="scss">
.social-media-links {
  width: fit-content;
}
.social-link {
  span {
    position: relative;
    transition: 0.3s all ease-in;
    &:after {
      content: '';
      height: 1px;
      width: 0;
      background: $primary;
      position: absolute;
      bottom: 0;
      left: 0;
      transition: all 0.3s ease;
    }
  }
  &:hover {
    span:after {
      width: 100%;
    }
  }
}
</style>
