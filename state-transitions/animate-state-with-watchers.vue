<template>
    <div id="animated-number-demo">
        <input 
            type="number"
            v-model.number="number"
            step="20" />

        <p>
            {{ animatedNumber }}
        </p>
    </div>
</template>

<script>
export default {
    setup() {
        const Demo = {
            data() {
                return {
                    number: 0,
                    tweenedNumber: 0
                }
            },

            computed: {
                animatedNumber(){
                    return this.tweenedNumber.toFixed(0)
                }
            },

            watch: {
                number(newValue) {
                    gsap.to(this.$data, {duration: 0.5, tweenedNumber: newValue })
                }
            }
        }

        Vue.createApp(Demo).mount('#animated-number-demo')
    }
}
</script>

<style scoped>

</style>