<template>
    <div id="demo">
        <input v-model="query" />  

        <transition-group
         name="staggered-fade"
         tag="ul"
         :css="false"
         @before-enter="beforeEnter"
         @enter="enter"
         @leave="leave">

         <li
         v-for="(item, index) in computedList"
            :key="item.msg"
            :data-index="index">
             {{ item.msg }}
         </li>
        
        </transition-group> 
    </div>
</template>

<script>
export default {
    setup() {
        const Demo = {
            data() {
                return {
                    query: '',
                    list: [
                        { msg: 'Bruce Lee' },
                        { msg: 'Jackie Chan' },
                        { msg: 'Chuck Norris' },
                        { msg: 'Jet Li' },
                        { msg: 'Kung Fury' }
                    ]
                }
            },

            computed: {
                computedList() {
                    var vm = this
                    return this.list.filter(item => {
                        return item.msg.toLowerCase().indexOf(vm.query.toLowerCase()) !== -1
                    })
                }
            },

            methods: {
                beforeEnter(el) {
                    el.style.opacity = 0
                    el.style.height = 0
                },

                enter(el, done) {
                    gsap.to(el, {
                        opacity: 1,
                        height: '1.6em',
                        delay: el.dataset.index * 0.15,
                        onComplete: done
                    })
                },

                leave(el, done) {
                    gsap.to(el, {
                        opacity: 0,
                        height: 0,
                        delay: el.dataset.index * 0.15,
                        onComplete: done
                    })
                }
            },
        }

        Vue.createApp(Demo).mount('#demo')
    }
    
}
</script>

<style scoped>

</style>