<template>
    <div id="demo">
        Push this button to do something you shouldn't be doing:
        <br />

        <div :class="{ shake: noActivated }">
            <button @click="noActivated = true">Click Me</button>
            <span v-if="noActivated">Ghai Zii!</span>
        </div>
        
    </div>
</template>

<script>

import Vue from 'vue';


export default {

    data() {
        return {
            noActivated: false
        }
    },
    
   
}

Vue.createApp(Demo).mount('#demo');

</script>

<style scoped>
.shake {
    animation: shake 0.82s cubic-bezier(0.36, 0.07, 0.19, 0.97) both;
    transform: translate3d(0, 0, 0);
    backface-visibility: hidden;
    perspective: 1000px;
}

@keyframes shakes {
    10%,
    90% {
        transform: translate3d(-1px, 0, 0);
    }

    20%,
    80% {
        transform: translate3d(2px, 0, 0);
    }

    30%,
    50%,
    70% {
        transform: translate3d(-4px, 0, 0);
    }

    40%,
    60% {
        transform: translate3d(4px, 0, 0);
    }
}
</style>