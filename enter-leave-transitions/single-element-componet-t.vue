<template>
    <div id="demo">
        <button @click="show = !show">
            Toggle
        </button>

        <transition name="fade">
            <p v-if="show">Habari</p>
        </transition>

    </div>
</template>

<script>
import Vue from 'vue';

export default {

    setup(props) {
        const Demo = {
        data() {
            return {
                show: true
            }
        },
    }
    }
    
}

Vue.createApp(Demo).mount('#demo')
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}
</style>