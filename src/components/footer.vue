<script>
import {
  FacebookIcon,
  TwitterIcon,
  InstagramIcon,
  LinkedinIcon,
} from 'vue-feather-icons';
export default {
  components: {
    FacebookIcon,
    TwitterIcon,
    InstagramIcon,
    LinkedinIcon,
  },
};
</script>

<template>
  <div>
    <!-- Footer Start -->
    <div class="footer-alt py-3">
      <div class="container">
        <div class="row">
          <div class="col-lg-12">
            <div class="text-center">
              <p class="text-white-50 font-size-15 mb-0">
                {{ new Date().getFullYear() }} © Palms and Dates
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- Footer End -->
  </div>
</template>
