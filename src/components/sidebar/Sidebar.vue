<template>
  <div class="absolute top-0 right-0 opacity-5">
    <img src="../../assets/code2.png" height="666" width="1000" alt="Code Background"/>
  </div>
  <div @mouseover="sidebarOpen" @mouseleave="sidebarClose" :style="{ width: sidebarWidth }"
       class="fixed top-0 bottom-0 left-0 z-50 transition duration-500 text-mj-lavender bg-mj-raisin-dark overflow-x-hidden border-r-2 border-mj-php-mellow transform -translate-x-1 xl:translate-x-0">
    <h2 class="text-center">
      <img src="../../assets/logo.png" alt="MJ Logo" class="m-auto p-2 max-h-24">
<!--      <span v-if="!menuOpen" class="mb-14 block">mj</span>-->
<!--      <span v-else class="text-5xl text-center mb-8 block">-mj-</span>-->
    </h2>

    <nav class="absolute top-24 left-0">
      <ul class="gap-5">
        <li>
          <a @click="sidebarClose" class="flex items-center border-2 p-2 mx-2 my-4 rounded-md border-mj-raisin-dark hover:border-mj-php-mellow transition-all" href="#hero" title="Home">
            <HomeIcon class="w-7 h-7 text-mj-lavender"/>
            <span v-if="menuOpen" class="ml-3">Home</span>
          </a>
        </li>
        <li>
          <a @click="sidebarClose" class="flex items-center border-2 p-2 mx-2 my-4 rounded-md border-mj-raisin-dark hover:border-mj-php-mellow transition-all" href="#about" title="About">
            <UserIcon class="w-7 h-7 text-mj-lavender"/>
            <span v-if="menuOpen" class="ml-3">About</span>
          </a>
        </li>
        <li>
          <a @click="sidebarClose" class="flex items-center border-2 p-2 mx-2 my-4 rounded-md border-mj-raisin-dark hover:border-mj-php-mellow transition-all" href="#skills" title="Skills">
            <LibraryIcon class="w-7 h-7 text-mj-lavender"/>
            <span v-if="menuOpen" class="ml-3">Skills</span>
          </a>
        </li>
        <li>
          <a @click="sidebarClose" class="flex items-center border-2 p-2 mx-2 my-4 rounded-md border-mj-raisin-dark hover:border-mj-php-mellow transition-all" href="#projects" title="Projects">
            <DesktopComputerIcon class="w-7 h-7 text-mj-lavender"/>
            <span v-if="menuOpen" class="ml-3">Projects</span>
          </a>
        </li>
        <li>
          <a @click="sidebarClose" class="flex items-center border-2 p-2 mx-2 my-4 rounded-md border-mj-raisin-dark hover:border-mj-php-mellow transition-all" href="#contact" title="Contact">
            <PhoneIcon class="w-7 h-7 text-mj-lavender"/>
            <span v-if="menuOpen" class="ml-3">Contact</span>
          </a>
        </li>
      </ul>
    </nav>
  </div>

  <div class="fixed top-5 right-5 xl:hidden z-50"       :class="{ 'hidden': !showHam }">
    <MenuIcon class="w-8 h-8 cursor-pointer text-mj-burgundy" @click="sidebarOpen"/>
  </div>

  <ul class="hidden xl:block fixed top-1/2 right-4 flex justify-center flex-col items-center transform -translate-y-1/2">
    <li class="mb-4"><a href="https://github.com/mjurkian" rel="noopener" title="GitHub" target="_blank" class="transition duration-200 hover:text-mj-php-mellow"><svg xmlns="http://www.w3.org/2000/svg" role="img" viewBox="0 0 24 24" width="28px" height="28px" fill="none" stroke="#E9EBF8" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round" class="stroke-current transition-all"><title>GitHub</title><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path></svg></a></li>
    <li class="mb-4"><a href="https://www.linkedin.com/in/michal-jurkian/" rel="noopener" title="LinkedIn" target="_blank" class="transition duration-200 hover:text-mj-php-mellow"><svg fill="#E9EBF8" stroke-width="1"  xmlns="http://www.w3.org/2000/svg" class="stroke-current fill-current"  viewBox="0 0 50 50" width="28px" height="28px"><path d="M 8 3.0117188 C 6.3126093 3.0117188 4.8354789 3.4916328 3.7539062 4.3652344 C 2.6723337 5.238836 2.0117188 6.533218 2.0117188 7.9472656 C 2.0117188 10.690836 4.4687078 12.814467 7.7167969 12.941406 A 0.98809878 0.98809878 0 0 0 8 12.988281 C 9.753566 12.988281 11.246191 12.474267 12.3125 11.564453 C 13.378809 10.654639 13.988281 9.3429353 13.988281 7.9472656 A 0.98809878 0.98809878 0 0 0 13.986328 7.8925781 C 13.832307 5.1316834 11.374781 3.0117187 8 3.0117188 z M 8 4.9882812 C 10.60907 4.9882812 11.895883 6.2693448 12.005859 7.9726562 C 11.998759 8.8049335 11.676559 9.5118991 11.03125 10.0625 C 10.378809 10.619186 9.371434 11.011719 8 11.011719 C 5.3980542 11.011719 3.9882813 9.5991704 3.9882812 7.9472656 C 3.9882812 7.1213132 4.3276663 6.4422421 4.9960938 5.9023438 C 5.6645211 5.3624454 6.6873907 4.9882813 8 4.9882812 z M 3 15 A 1.0001 1.0001 0 0 0 2 16 L 2 45 A 1.0001 1.0001 0 0 0 3 46 L 13 46 A 1.0001 1.0001 0 0 0 14 45 L 14 35.664062 L 14 16 A 1.0001 1.0001 0 0 0 13 15 L 3 15 z M 18 15 A 1.0001 1.0001 0 0 0 17 16 L 17 45 A 1.0001 1.0001 0 0 0 18 46 L 28 46 A 1.0001 1.0001 0 0 0 29 45 L 29 29 L 29 28.75 L 29 28.5 C 29 26.555577 30.555577 25 32.5 25 C 34.444423 25 36 26.555577 36 28.5 L 36 45 A 1.0001 1.0001 0 0 0 37 46 L 47 46 A 1.0001 1.0001 0 0 0 48 45 L 48 28 C 48 23.873476 46.787888 20.604454 44.744141 18.375 C 42.700394 16.145546 39.849212 15 36.787109 15 C 32.882872 15 30.521631 16.426076 29 17.601562 L 29 16 A 1.0001 1.0001 0 0 0 28 15 L 18 15 z M 4 17 L 12 17 L 12 35.664062 L 12 44 L 4 44 L 4 17 z M 19 17 L 27 17 L 27 19.638672 A 1.0001 1.0001 0 0 0 28.744141 20.306641 C 28.744141 20.306641 31.709841 17 36.787109 17 C 39.360007 17 41.615528 17.922268 43.269531 19.726562 C 44.923534 21.530858 46 24.261524 46 28 L 46 44 L 38 44 L 38 28.5 A 1.0001 1.0001 0 0 0 37.916016 28.089844 C 37.694061 25.26411 35.38033 23 32.5 23 C 29.474423 23 27 25.474423 27 28.5 L 27 28.75 L 27 29 L 27 44 L 19 44 L 19 17 z"/></svg>
    </a></li>
    <li><a href="https://twitter.com/mjurkian" rel="noopener" title="Twitter" target="_blank" class="transition duration-200 hover:text-mj-php-mellow"><svg fill="#E9EBF8" stroke-width="1" xmlns="http://www.w3.org/2000/svg" class="stroke-current fill-current"  viewBox="0 0 50 50" width="28px" height="28px"><path d="M 34.21875 5.46875 C 28.238281 5.46875 23.375 10.332031 23.375 16.3125 C 23.375 16.671875 23.464844 17.023438 23.5 17.375 C 16.105469 16.667969 9.566406 13.105469 5.125 7.65625 C 4.917969 7.394531 4.597656 7.253906 4.261719 7.277344 C 3.929688 7.300781 3.632813 7.492188 3.46875 7.78125 C 2.535156 9.386719 2 11.234375 2 13.21875 C 2 15.621094 2.859375 17.820313 4.1875 19.625 C 3.929688 19.511719 3.648438 19.449219 3.40625 19.3125 C 3.097656 19.148438 2.726563 19.15625 2.425781 19.335938 C 2.125 19.515625 1.941406 19.839844 1.9375 20.1875 L 1.9375 20.3125 C 1.9375 23.996094 3.84375 27.195313 6.65625 29.15625 C 6.625 29.152344 6.59375 29.164063 6.5625 29.15625 C 6.21875 29.097656 5.871094 29.21875 5.640625 29.480469 C 5.410156 29.742188 5.335938 30.105469 5.4375 30.4375 C 6.554688 33.910156 9.40625 36.5625 12.9375 37.53125 C 10.125 39.203125 6.863281 40.1875 3.34375 40.1875 C 2.582031 40.1875 1.851563 40.148438 1.125 40.0625 C 0.65625 40 0.207031 40.273438 0.0507813 40.71875 C -0.109375 41.164063 0.0664063 41.660156 0.46875 41.90625 C 4.980469 44.800781 10.335938 46.5 16.09375 46.5 C 25.425781 46.5 32.746094 42.601563 37.65625 37.03125 C 42.566406 31.460938 45.125 24.226563 45.125 17.46875 C 45.125 17.183594 45.101563 16.90625 45.09375 16.625 C 46.925781 15.222656 48.5625 13.578125 49.84375 11.65625 C 50.097656 11.285156 50.070313 10.789063 49.777344 10.445313 C 49.488281 10.101563 49 9.996094 48.59375 10.1875 C 48.078125 10.417969 47.476563 10.441406 46.9375 10.625 C 47.648438 9.675781 48.257813 8.652344 48.625 7.5 C 48.75 7.105469 48.613281 6.671875 48.289063 6.414063 C 47.964844 6.160156 47.511719 6.128906 47.15625 6.34375 C 45.449219 7.355469 43.558594 8.066406 41.5625 8.5 C 39.625 6.6875 37.074219 5.46875 34.21875 5.46875 Z M 34.21875 7.46875 C 36.769531 7.46875 39.074219 8.558594 40.6875 10.28125 C 40.929688 10.53125 41.285156 10.636719 41.625 10.5625 C 42.929688 10.304688 44.167969 9.925781 45.375 9.4375 C 44.679688 10.375 43.820313 11.175781 42.8125 11.78125 C 42.355469 12.003906 42.140625 12.53125 42.308594 13.011719 C 42.472656 13.488281 42.972656 13.765625 43.46875 13.65625 C 44.46875 13.535156 45.359375 13.128906 46.3125 12.875 C 45.457031 13.800781 44.519531 14.636719 43.5 15.375 C 43.222656 15.578125 43.070313 15.90625 43.09375 16.25 C 43.109375 16.65625 43.125 17.058594 43.125 17.46875 C 43.125 23.71875 40.726563 30.503906 36.15625 35.6875 C 31.585938 40.871094 24.875 44.5 16.09375 44.5 C 12.105469 44.5 8.339844 43.617188 4.9375 42.0625 C 9.15625 41.738281 13.046875 40.246094 16.1875 37.78125 C 16.515625 37.519531 16.644531 37.082031 16.511719 36.683594 C 16.378906 36.285156 16.011719 36.011719 15.59375 36 C 12.296875 35.941406 9.535156 34.023438 8.0625 31.3125 C 8.117188 31.3125 8.164063 31.3125 8.21875 31.3125 C 9.207031 31.3125 10.183594 31.1875 11.09375 30.9375 C 11.53125 30.808594 11.832031 30.402344 11.816406 29.945313 C 11.800781 29.488281 11.476563 29.097656 11.03125 29 C 7.472656 28.28125 4.804688 25.382813 4.1875 21.78125 C 5.195313 22.128906 6.226563 22.402344 7.34375 22.4375 C 7.800781 22.464844 8.214844 22.179688 8.355469 21.746094 C 8.496094 21.3125 8.324219 20.835938 7.9375 20.59375 C 5.5625 19.003906 4 16.296875 4 13.21875 C 4 12.078125 4.296875 11.03125 4.6875 10.03125 C 9.6875 15.519531 16.6875 19.164063 24.59375 19.5625 C 24.90625 19.578125 25.210938 19.449219 25.414063 19.210938 C 25.617188 18.96875 25.695313 18.648438 25.625 18.34375 C 25.472656 17.695313 25.375 17.007813 25.375 16.3125 C 25.375 11.414063 29.320313 7.46875 34.21875 7.46875 Z"/></svg>
    </a></li>
  </ul>
</template>

<script>
import {
  DesktopComputerIcon,
  HomeIcon,
  LibraryIcon,
  MenuIcon,
  PhoneIcon,
  UserIcon
} from '@heroicons/vue/outline'


export default {
  name: "Sidebar",
  props: {},
  components: {
    HomeIcon,
    UserIcon,
    DesktopComputerIcon,
    PhoneIcon,
    MenuIcon,
    LibraryIcon
  },
  data() {
    return {
      menuOpen: false,
      sidebarWidth: '',
      mobile: true,
      showHam: true,
      lastScrollPosition: 0
    }
  },
  mounted() {
    window.addEventListener('resize', this.sidebarClose);
    window.addEventListener('scroll', this.onScroll);

    if (this.isMobile()) {
      this.sidebarWidth = 0
    } else {
      this.sidebarWidth = '68px'
      this.mobile = false
    }
  },
  methods: {
    isMobile() {
      return screen.width <= 1155;
    },

    sidebarOpen() {
      this.menuOpen = true
      this.sidebarWidth = '160px'
    },

    sidebarClose() {
      this.menuOpen = false

      if (this.isMobile()) {
        this.sidebarWidth = '0'
      } else {
        this.sidebarWidth = '68px'
      }
    },

    onScroll () {
      const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop
      if (currentScrollPosition < 0) {
        return
      }
      if (Math.abs(currentScrollPosition - this.lastScrollPosition) < 60) {
        return
      }
      this.showHam = currentScrollPosition < this.lastScrollPosition
      this.lastScrollPosition = currentScrollPosition
    }
  }
}
</script>
