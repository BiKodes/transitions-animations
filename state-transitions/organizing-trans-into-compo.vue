<template>
    <div id="app">
        <input type="number" step="20" v-model.number="firstNumber"> +
        <input type="number" step="20" v-model.number="secondNumber"> = {{ result }}

        <p>
            <animated-integer :value="firstNumber"></animated-integer> +
            <animated-integer :value="secondNumber"></animated-integer> =
            <animated-integer :value="result"></animated-integer>
        </p>
    </div>
</template>

<script>
export default {
    setup() {
        const app = Vue.createApp({
            data() {
                return {
                    firstNumber: 20,
                    secondNumber: 40
                }
            },

            computed: {
                result() {
                    return this.firstNumber + this.secondNumber
                }
            }
        })

        app.component('animated-integer', {
            template: '<span>{{ fullValue }}</span>',
            props: {
                value: {
                    type: Number,
                    required: true
                }
            },

            data() {
                return {
                    tweeningValue: 0
                }
            },

            computed: {
                fullValue(){
                    return Math.floor(this.tweeningValue)
                }
            },

            methods: {
                tween(newValue, oldValue) {
                    gsap.to(this.$data, {
                        duration: 0.5,
                        tweeningValue: newValue,
                        ease: 'sine'
                    })
                }
            },

            watch: {
                value(newValue, oldValue) {
                    this.tween(newValue, oldValue)
                }
            },

            mounted() {
                this.tween(this.value, 0)
            },
        })

        app.mount('#app')
    }
}
</script>