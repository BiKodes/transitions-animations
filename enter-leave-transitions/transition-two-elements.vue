<template>
    <div id="demo">
        <transition>
            <table v-if="items.length > 0">

            </table>

            <p v-else>Sorry, no items found.</p>
        </transition>
    </div>
</template>

<script>

export default {
    
}
</script>