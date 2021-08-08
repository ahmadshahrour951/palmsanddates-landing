<script>
import Navbar from '@/components/navbar';
import Service from '@/components/services';
import Features from '@/components/features';
import Contact from '@/components/contact';
import Footer from '@/components/footer';

import { BSpinner } from 'bootstrap-vue';

/**
 * Index-1
 */
export default {
  components: { Navbar, Service, Features, Contact, Footer, BSpinner },
  data() {
    return {
      isSending: false,
      email: '',
    };
  },
  methods: {
    async sendSubscription() {
      try {
        this.isSending = true;
        await this.axios.post('/mail/subscribe', { email: this.email });
        this.isSending = false;
        this.email = '';
      } catch (err) {
        console.log(error);
        this.isSending = false;
      }
    },
  },
};
</script>

<template>
  <div>
    <Navbar />
    <div v-scroll-spy>
      <!-- Hero Start -->
      <section
        class="hero-1-bg"
        :style="{
          'background-image':
            'url(' + require('@/assets/images/hero-1-bg-img.png') + ')',
          'z-index': '-1',
        }"
        id="home"
      >
        <div class="container">
          <div class="row align-items-center justify-content-center">
            <img
              src="@/assets/images/1234.png"
              class="img-responsive"
              width="900"
              style="position: absolute; z-index: 0; right: 10%; top: 25%;"
            />
            <div class="col-lg-8 mr-auto" style="position: relative;">
              <div class="card p-4 glass">
                <div class="card-body">
                  <h1 class="hero-1-title text-dark font-weight-bold mb-4">
                    Dorm Community Made Simple
                  </h1>
                  <div class="w-75 mb-5 mb-lg-0">
                    <p class="text-muted mb-5 pb-5 font-size-17">
                      Made for and by students. We're here to change the way we
                      socialize in our dorm residence.
                    </p>
                    <p class>Want to stay in the loop?</p>
                    <div class="subscribe-form">
                      <form action="#">
                        <input
                          type="text"
                          placeholder="Enter  email..."
                          v-model="email"
                        />
                        <button
                          type="submit"
                          class="btn btn-primary"
                          @click.prevent="sendSubscription"
                        >
                          <div class="text-center" v-if="!isSending">
                            Subscribe
                          </div>
                          <div v-else>
                            <b-spinner small label="Loading..."></b-spinner>
                          </div>
                        </button>
                      </form>
                    </div>
                  </div>
                </div>
              </div>
            </div>

            <!-- <div class="col-lg-6 col-md-10">
              <div class="mt-5 mt-lg-0">
                <img
                  src="@/assets/images/1234.png"
                  alt
                  class="img-fluid d-block mx-auto"
                />
              </div>
            </div> -->
          </div>
        </div>
      </section>
      <!-- Hero End -->
      <Service />
      <Features />
      <Contact />
      <Footer />
    </div>
  </div>
</template>
