<template>
    <div id="demo">
        <div
            @mousemove="xCordinate"
            :style="{ backgroundColor: `hsl(${x}, 80%, 50%)` }"
            class="movearea"
        >
            <h3>Move your mouse across the screen...</h3>
            <p>x: {{x}}</p>
        </div>
        
    </div>
</template>

<script>
export default {

    const Demo = {
        data() {
            return {
                x: 0
            }
        },

        methods: {
            xCordinate(e) {
                this.x = e.clientX
            }
        },
    }
    
}

Vue.createApp(Demo).mount('demo');

</script>

<style scoped>
.movearea {
    transition: 0.2s backgraound-color ease;
}
</style>