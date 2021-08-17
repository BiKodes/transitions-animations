<template>
    <div id="demo">
        <transition name="mode-fade" mode="out-in">
            <button v-if="on" key="on" @click="on=false">
                On
            </button>
            <button v-else key="off" @click="on = true">
                Off
            </button>
        </transition>
    </div>
</template>

<script>

export default {
    setup(props) {
        const  Demo = {
            data() {
                return {
                    on: false
                }
            },
        }

        Vue.createApp(Demo).mount('#demo')
    }    
}

</script>

<style scoped>
body {
    margin: 30px;
}

#demo {
    position: relative;
}

button {
    position: absolute;
}

.mode-fade-enter-active, 
.mode-fade-leave-active {
    transition: opacity .5s ease;
}

.mode-fade-enter-from,
.mode-fade-leave-to {
    opacity: 0;
}

button {
  background: #05ae7f;
  border-radius: 4px;
  display: inline-block;
  border: none;
  padding: 0.5rem 0.75rem;
  text-decoration: none;
  color: #ffffff;
  font-family: sans-serif;
  font-size: 1rem;
  cursor: pointer;
  text-align: center;
  -webkit-appearance: none;
  -moz-appearance: none;
}
</style>