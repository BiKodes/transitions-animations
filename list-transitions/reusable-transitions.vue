<template>
    <div>
        
    </div>
</template>

<script>
export default {
    setup() {
        
        Vue.component('my-special-transition', {
        template: `\
            <transition\
                name="very-special-transition"\
                mode="out-in"\
                @before-enter="beforeEnter"\
                @after-enter="afterEnter"\
                >\
                    <slot></slot>
                </transition>/
            `,

            methods: {
                beforeEnter(el) {

                },

                afterEnter(el) {

                }
            },
    })
    }
}
</script>

<style scoped>

</style>