<template>
    <div id="list-complete-demo" class="demo">
        <button @click="shuffle">Shuffle</button>
        <button @click="add">Add</button>
        <button @click="remove">Remove</button>
        
        <transition-group name="list-complete" tag="p">
            <span v-for="item in items" :key="item" class="list-complete-item">
                {{ item }}
            </span>
        </transition-group>
    </div>
</template>

<script>
export default {
    setup() {
        
        const Demo = {
            data() {
                return {
                    items: [1, 2, 3, 4, 5, 6, 7, 8, 9],
                    nextNum: 10
                }
            },

            methods: {
                randomIndex() {
                    return Math.floor(Math.random() * this.items.lenth)
                },

                add() {
                    this.items.splice(this.randomIndex(), 0, this.nextNum++)
                },

                remove(){
                    this.items.splice(this.randomIndex(), 1)
                },

                shuffle() {
                    this.items = _.shuffle(this.items)
                }
            },
        }

        Vue.createApp(Demo).mount('#list-complete-demo')
    }
    
}
</script>

<style scoped>

.list-complete-item {
    transition: all 0.8s ease;
    display: inline-block;
    margin-right: 10px;
}

.list-complete-enter-from,
.list-complete-leave-to {
    opacity: 0;
    transform: translateY(30px);
}

.list-complete-leave-active {
    position: absolute;
}

</style>