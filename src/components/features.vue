<script>
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiChartBubble } from '@mdi/js';
import {
  LayoutIcon,
  LifeBuoyIcon,
  ServerIcon,
  RssIcon,
} from 'vue-feather-icons';
export default {
  components: { LayoutIcon, LifeBuoyIcon, ServerIcon, RssIcon, SvgIcon },
  data() {
    return {
      path: mdiChartBubble,
    };
  },
};
</script>

<template>
  <div>
    <!-- Features Start -->
    <section
      class="section bg-light feather-bg-img"
      :style="{
        'background-image':
          'url(' + require('@/assets/images/features-bg-img.png') + ')',
      }"
      id="features"
    >
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-lg-6">
            <div class="text-center mb-5">
              <h3 class="title mb-3">It's a Win-Win Platform</h3>
              <p class="text-muted font-size-15">
                Whether you're a building manager or a student.
                <br />We got you covered.
              </p>
            </div>
          </div>
        </div>

        <div class="row align-items-center">
          <div class="col-lg-6">
            <div class="mb-4 mb-lg-0">
              <img
                src="@/assets/images/32594.png"
                alt
                class="img-fluid d-block mx-auto"
              />
            </div>
          </div>

          <div class="col-lg-5 offset-lg-1">
            <p class="font-weight-medium text-uppercase mb-2">
              <svg-icon
                type="mdi"
                :path="path"
                class="mdi h2 text-primary mr-1 align-middle"
              ></svg-icon
              >Students
            </p>
            <h3 class="font-weight-semibold line-height-1_4 mb-4">
              Build
              <b>Community</b> & <b>Long Lasting</b> Friendship
            </h3>
            <p class="text-muted font-size-15 mb-4 text-justify">
              You could be a senior or fresh off the boat; you'll be welcome all
              the same. In addition, you'd be able to scroll through student
              profiles to see who has similar interests and create groups or
              events with them.
            </p>
            <div class="mt-5">
              <a href="javascript: void(0);" class="btn btn-primary mr-2"
                >Subscribe</a
              >
            </div>
          </div>
        </div>
      </div>
    </section>

    <section
      class="section feather-bg-img"
      :style="{
        'background-image':
          'url(' + require('@/assets/images/features-bg-img-1.png') + ')',
      }"
    >
      <div class="container">
        <div class="row align-items-center">
          <div class="col-lg-5">
            <p class="font-weight-medium text-uppercase mb-2">
              <i
                class="mdi mdi-chart-bubble h2 text-primary mr-1 align-middle"
              ></i>
              Building Managers
            </p>
            <h3 class="font-weight-semibold line-height-1_4 mb-4">
              Retain Students & Manage With Ease
            </h3>
            <p class="text-muted font-size-15 mb-4 text-justify">
              Create a safe & social environment for students, and a happy
              student is a recurring tenant. You can also nurture a relationship
              with the tenants by communication and events in the residence.
            </p>
            <div class="mt-5">
              <a href="javascript: void(0);" class="btn btn-primary mr-2"
                >Subscribe</a
              >
            </div>
          </div>
          <div class="col-lg-6 offset-lg-1">
            <div class="mt-4 mt-lg-0">
              <img
                src="@/assets/images/5576.png"
                alt
                class="img-fluid d-block mx-auto"
              />
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- Features End -->
  </div>
</template>
