<template>
    <div id="demo" class="demo">
        <input v-model="view" type="radio" value="v-a" id="a"><label for="a">A</label>
        <input v-model="view" type="radio" value="v-b" id="b"><label for="b">B</label>

        <transition name="component-fade" mode="out-in">
            <component :is="view"></component>
        </transition>
    </div>
</template>

<script>
export default {
    setup() {
        const Demo = {
        data() {
            return {
            view: "v-a"
            };
        },

        components: {
            "v-a": {
            template: "<div>Component A</div>"
            },
            "v-b": {
            template: "<div>Component B</div>"
            }
        }
        };
    }
}
</script>

<style scoped>
.component-fade-enter-active,
.component-fade-leave-active {
  transition: opacity 0.3s ease;
}

.component-fade-enter-from,
.component-fade-leave-to {
  opacity: 0;
}

.demo {
  font-family: sans-serif;
  border: 1px solid #eee;
  border-radius: 2px;
  padding: 20px 30px;
  margin-top: 1em;
  margin-bottom: 40px;
  user-select: none;
  overflow-x: auto;
}

</style>