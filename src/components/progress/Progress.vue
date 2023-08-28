<template>
  <div class="stat-circle" :class="{ 'animate': isAnimated }">
    <svg class="stat-circle" width="180" viewBox="0 0 20 20">
      <circle class="bg" cx="10" cy="10" r="8"></circle>
      <circle class="progress" cx="10" cy="10" r="8" :style="progressStyle"></circle>
      <text x="50%" y="55%">{{ currentPercentage }}%</text>
    </svg>
  </div>
</template>

<script>
export default {
  props: ["percentage"],
  data() {
    return {
      isAnimated: false,
      currentPercentage: 0,
      observer: null,
    };
  },
  mounted() {
    this.observer = new IntersectionObserver(this.handleIntersection, {
      threshold: 0.2
    });
    const section = document.querySelector(".stat-circle");
    if (section) {
      this.observer.observe(section);
    } 
  },
  methods: {
    handleIntersection(entries) {
      if (entries[0].isIntersecting) {
        this.isAnimated = true;
        this.changePercentage();
      }
      else {
        this.isAnimated = false;
      }
      
    },
    changePercentage(){
      setInterval(()=>{
        if(this.currentPercentage < this.percentage){
          this.currentPercentage++; 
        }
      }, 10);

    }
  },
  computed:{
    progressStyle() {
      const offset = 51 - (51 * (this.percentage / 100));
        return {
          strokeDashoffset: offset,
          transition: "stroke-dashoffset 0.4s ease",
      };
    },
  },

};
</script>

<style>

</style>
