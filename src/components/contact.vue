<script>
import {
  SendIcon,
  MailIcon,
  LinkIcon,
  PhoneCallIcon,
  ClockIcon,
  MapPinIcon,
} from 'vue-feather-icons';

import { BSpinner } from 'bootstrap-vue';

export default {
  components: {
    SendIcon,
    MailIcon,
    LinkIcon,
    PhoneCallIcon,
    ClockIcon,
    MapPinIcon,
    BSpinner,
  },
  data() {
    return {
      isSending: false,
      name: '',
      email: '',
      message: '',
    };
  },
  methods: {
    async sendContactUs() {
      try {
        const data = {
          name: this.name,
          email: this.email,
          message: this.message,
        };
        this.isSending = true;
        await this.axios.post('/mail/contact-us', data);
        this.isSending = false;
        this.name = '';
        this.email = '';
        this.message = '';
      } catch (error) {
        console.log(error);
        this.isSending = false;
      }
    },
  },
};
</script>
<template>
  <!-- Contact Us Start -->
  <section class="section bg-light" id="contact">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-lg-6">
          <div class="text-center mb-5">
            <h3 class="title mb-3">Contact Us</h3>
            <p class="text-muted font-size-15">
              We love attention, especially if it's from an early adopter. Send
              us a message and we'll get back to you as soon as possible.
            </p>
          </div>
        </div>
      </div>
      <div class="row align-items-center">
        <div class="col-lg-6 mx-auto">
          <div class="custom-form mb-5 mb-lg-0">
            <div id="message"></div>

            <form name="contact-form" id="contact-form">
              <div class="row">
                <div class="col-md-6">
                  <div class="form-group">
                    <label for="name">Name*</label>
                    <input
                      id="name"
                      type="text"
                      class="form-control"
                      placeholder="Your name..."
                      v-model="name"
                    />
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="form-group">
                    <label for="email">Email Address*</label>
                    <input
                      id="email"
                      type="email"
                      class="form-control"
                      placeholder="Your email..."
                      v-model="email"
                    />
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-lg-12">
                  <div class="form-group">
                    <label for="comments">Message*</label>
                    <textarea
                      id="comments"
                      rows="4"
                      class="form-control"
                      placeholder="Your message..."
                      v-model="message"
                    ></textarea>
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-sm-12">
                  <button
                    type="button"
                    class="btn btn-primary w-100"
                    @click.prevent="sendContactUs"
                  >
                    <div class="text-center" v-if="!isSending">
                      Send Message
                      <send-icon class="icon-size-15 ml-2 icon"></send-icon>
                    </div>
                    <div v-else>
                      <b-spinner small label="Loading..."></b-spinner>
                    </div>
                  </button>
                  <div id="simple-msg"></div>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>
  <!-- Contact Us End -->
</template>
