<template>
    <div>
        <transition-group tag="div" name="list">
            <span 
                class="list-item mx-1" 
                v-for="number in numbers" 
                :key="number"
            >
                {{ number }}
            </span>
        </transition-group>
        


        <div class="mt-3">
            <button @click.prevent="onAdd()">Add</button>
            <button @click.prevent="onRemove()">Remove</button>
            <button @click.prevent="onShuffle()">Shuffle</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ListData',

    data() {
        return {
            numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9],
            nextNum: 10,
        }
    },

    methods: {
        onAdd() {
            this.numbers.push(this.nextNum);
            this.nextNum++;
        },

        onRemove(){
            let randomIndex = Math.floor(Math.random() * this.numbers.length);

            this.numbers = this.numbers.filter(
                (number) => number !== this.numbers[randomIndex]
            );
        },

        onShuffle() {
            this.numbers.reverse();
        }


    }
    
}
</script>

<style scoped>
.list-item {
    display: inline-block;
}

.list-enter-from {
    opacity: 0;
    transform: translateY(30px);
}

.list-enter-to {
    opacity: 1;
    transform: translateY(0px);
}

.list-enter-active {
    transition: all 1s ease-in;
}

.list-leave-from{
    opacity: 1;
    transform: translateY(0px);
}

.list-leave-to {
    opacity: 0;
    transform: translateY(30px);
}

.list-leave-active {
    transition: all 1s ease-out;
    position: absolute;
}

.list-move {
    transition: transform 1s ease;
}
</style>