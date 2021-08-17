<template>
    <div id="flip-list-demo">
        <button @click="shuffle">Shuffle</button>

        <transition-group name="flip-list" tag="ul">
            <li v-for="item in items" :key="item">
                {{ item }}
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
                    items: [1, 2, 3, 4, 5, 6, 7, 8, 9]
                }
            },

            methods: {
                shuffle() {
                    this.items = _.shuffle(this.items)
                }
            },
        }

        Vue.createApp(Demo).mount('#flip-list-demo')
    }
}
</script>

<style scoped>
.flip-list-move {
    transition: transform 0.8s ease;
}
</style>