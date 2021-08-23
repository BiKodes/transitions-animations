<template>
  <div class="container">

    <div class="row">
      <div class="col-md-12">
        <router-view v-slot="{ Component }">
          <transition name="fade" mode="out-in">
            <component :is="Component" />
          </transition>
        </router-view>
      </div>
    </div>

    <!-- <div class="row">
      <div class="col-md-6">
          <div class="box" :class="{ animate: animate }"></div>
          <div class="my-3"> <br>
            <button 
              class="btn btn-primary" 
              @click.prevent="onAnimateClick()"
            >
              Nifinye
            </button>
          </div> 

          <div class="my-3">
            <animate-button></animate-button>
          </div> 

          <div class="my-3">
            <the-paragraph></the-paragraph>
          </div>  

           <div class="my-3">
            <animate-paragraph></animate-paragraph>
          </div> 

        
      </div>

      <div class="col-md-6">
        <div class="my-3">
          <transition-events></transition-events>
        </div>

        <div class="my-3">
          <list-data></list-data>
        </div>
      </div>

     
    </div> -->

 
  </div>
</template>

<script>
// import TheParagraph from './components/TheParagraph.vue'
// import AnimateParagraph from './components/AnimateParagraph.vue'
// import AnimateButton from './components/AnimateButton.vue'
// import TransitionEvents from './components/TrasitionEvents.vue'
// import ListData from './components/ListData.vue'


export default {
  name: 'App',

  components: {
    // TheParagraph,
    // AnimateParagraph,
    // AnimateButton,
    // TransitionEvents,
    // ListData
  },

  data(){
    return {
      animate: false
    }
  },
  
  methods: {
    onAnimateClick() {
      this.animate = true
    }
  }
}
</script>

<style>
.box {
  width: 100px;
  height: 100px;
  border: 1px solid red;
  background: red;
  /* transition: transform 0.5s; */
}

.animate {
  /* transform: translateX(150px); */
  animation: animate-box 1s forwards;
}

@keyframes animate-box {
  0% {
    transform: translateX(0px) scaleX(1);
  }
  50% {
    transform: translateX(100px) scaleX(1.5);
  }
  100% {
    transform: translateX(200px) scaleX(1);
  }
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateX(-100px);
}

.fade-enter-to,
.fade-leave-from {
  opacity: 1;
  transform: translateX(0px);
}

.fade-enter-active,
.fade-leave-active {
  transition: all 0.5s ease;
}
</style>
