<script>
import {
  ArrowRightCircleIcon,
} from 'vue-feather-icons';

export default {
  props: {
    navbarcolor: {
      type: Boolean,
      default: false,
    },
  },
  components: {
    ArrowRightCircleIcon,
  },
  mounted: () => {
    window.onscroll = function() {
      onwindowScroll();
    };
    var navbar = document.getElementById('navbar');
    function onwindowScroll() {
      if (
        document.body.scrollTop > 50 ||
        document.documentElement.scrollTop > 50
      ) {
        navbar.classList.add('nav-sticky');
      } else {
        navbar.classList.remove('nav-sticky');
      }
    }
  },
  methods: {
    /**
     * Toggle menu
     */
    toggleMenu() {
      document.getElementById('navbarCollapse').classList.toggle('show');
    },
  },
};
</script>

<template>
  <!--Navbar Start-->
  <nav
    class="navbar navbar-expand-lg fixed-top navbar-custom sticky sticky-dark"
    id="navbar"
    :class="{ 'navbar-light': navbarcolor === true }"
  >
    <div class="container">
      <!-- LOGO -->
      <a class="navbar-brand logo" href="/">
        <img
          src="@/assets/images/logo-dark.png"
          alt
          class="logo-dark"
          height="24"
        />
        <img
          src="@/assets/images/logo-light.png"
          alt
          class="logo-light"
          height="24"
        />
      </a>
      <button
        class="navbar-toggler"
        type="button"
        @click="toggleMenu()"
        aria-label="Toggle navigation"
      >
        <i class="mdi mdi-menu"></i>
      </button>
      <div class="collapse navbar-collapse" id="navbarCollapse">
        <ul
          class="navbar-nav ml-auto navbar-center"
          id="mySidenav"
          v-scroll-spy-active
        >
          <li class="nav-item">
            <a
              href="javascript: void(0);"
              v-scroll-to="'#home'"
              class="nav-link"
              >Home</a
            >
          </li>
          <li class="nav-item">
            <a
              href="javascript: void(0);"
              v-scroll-to="{ el: '#features', offset: -2 }"
              class="nav-link"
              >Features</a
            >
          </li>
          <li class="nav-item">
            <a
              href="javascript: void(0);"
              v-scroll-to="{ el: '#contact', offset: -50 }"
              class="nav-link"
              >Contact Us</a
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
  <!-- Navbar End -->
</template>
