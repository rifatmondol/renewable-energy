<template>
  <div>
    <button id="topButton" @click="scrollToTop" v-show="showTopButton">
      <div class="progress-circle">
        <svg class="progress-svg" viewBox="0 0 100 100">
          <circle class="progress-background" cx="50" cy="50" r="45"></circle>
          <circle class="progress-bar" cx="50" cy="50" r="45" :stroke-dasharray="circleDashArray" :stroke-dashoffset="circleDashOffset"></circle>
        </svg>
        <font-awesome-icon icon="fa-solid fa-arrow-up" class="font"/>
        
      </div>
      
    </button>

    <!-- Your page content here -->

  </div>
</template>

<script>
export default {
  data() {
    return {
      showTopButton: false,
      progress: 0,
      circleDashArray: 283, // Circumference of a circle with radius 45
      circleDashOffset: 283
    };
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      const scrollY = window.scrollY;
      const windowHeight = window.innerHeight;
      const fullHeight = document.documentElement.scrollHeight;
      const scrolledPercentage = (scrollY / (fullHeight - windowHeight)) * 100;

      this.progress = scrolledPercentage;
      this.circleDashOffset = this.circleDashArray - (scrolledPercentage * this.circleDashArray) / 100;

      if (scrollY > windowHeight / 2) {
        this.showTopButton = true;
      } else {
        this.showTopButton = false;
      }
    },
    scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      });
    }
  }
};
</script>

<style>
#topButton {
  position: fixed;
  bottom: 20px;
  right: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  background-color: transparent;
  /* border: 2px solid #3498db; */
  border: none;
  padding: 0;
  cursor: pointer;
  z-index: 9999;
}

.progress-circle {
  position: relative;
  width: 60px;
  height: 60px;
}

.progress-svg {
  width: 100%;
  height: 100%;
}
.progress-circle .font{
  position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%,-50%);
    font-size: 20px;
    color: var(--light-green);
    opacity: 0.5;
    transition: 0.2s;
}
.progress-circle:hover .font{
  opacity: 1;
}
.progress-background {
  fill: none;
  stroke: var(--extra-light-green);
  stroke-width: 4;
}

.progress-bar {
    fill: none;
    stroke: var(--light-green);
    stroke-width: 8px;
    transform: translate(0px, 0px);
    transition: stroke-dashoffset 0.3s ease;
}
</style>
