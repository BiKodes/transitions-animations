<template>
    <div id="demo">
        <button @click="show = !show">
            Finya Render
        </button>

        <transition name="slide-fade">
            <p v-if="show">Habari</p>
        </transition>
        
    </div>
</template>

<script>


export default {
   setup() {
       
       const Demo = {
           data() {
               return {
                   show: true
               }
           },
       }

       Vue.createApp(Demo).mount('#demo')
   } 
}
</script>

<style scoped>

/* Enter and leave animations can use different */
/* durations and timing functions.              */

.slide-fade-enter-active {
    transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
    transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-active,
.slide-fade-leave-active {
    transform: translateX(20px);
    opacity: 0;
}

</style>