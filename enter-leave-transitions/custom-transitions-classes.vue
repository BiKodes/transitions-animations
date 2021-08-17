<template>
    <div id="demo">
        <button @click="show = !show">
            BOnyeza Render
        </button>

        <transition
         name="custom-classes-transition"
         enter-active-class="animate__animated animated__tada"
         leave-active-class="animate__animated animated__bounceOutRight"
         >
            <p v-if="show">Habari Gani</p>
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