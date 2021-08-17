<template>
    <div id="dynamic-fade-demo" class="demo">
        Fade In:
        <input type="range" v-model="fadeInDuration" min="0" :max="maxFadeDuration"/>
        Fade Out:

        <input 
            type="range"
            v-model="fadeOutDuration"
            min="0"
            :max="maxFadeDuration"
        />

        <transition
            :css="false"
            @before-enter="beforeEnter"
            @enter="enter"
            @leave="leave"
        >
            <p v-if="show">Habari Yako</p>
        </transition>

        <button v-if="stop" @click="stop = false; show =false">
            Start Animating
        </button>

        <button v-else @click="stop =true">Stop It!</button>
        
    </div>
</template>

<script>
export default {

    setup() {
        const app = Vue.createApp({
            data() {
                return {
                    show: true,
                    fadeInDuration: 1000,
                    fadeOutDuration: 1000,
                    maxFadeDuration: 1500,
                    stop: true
                }
            },

            mounted() {
                this.show = false
            },

            methods: {
                beforeEnter(el){
                    el.style.opacity = 0
                },

                enter(el, done){
                    var vm = this

                    velocity(
                        el,
                        { opacity: 1 },
                        {
                            duration: this.fadeInDuration,
                            complete: function(){
                                done()
                                if (!vm.stop) vm.show = false
                            }
                        }
                    )
                },

                leave(el, done) {
                    var vm = this
                    velocity(
                        el,
                        { opacity: 0 },
                        {
                            duration: this.fadeOutDuration,
                            complete: function() {
                                done()
                                vm.show = true
                            }
                        }
                    )
                }
            },
        })

        app.mount('#dynamic-fade-demo')
    }
    
}
</script>