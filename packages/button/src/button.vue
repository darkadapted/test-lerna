<template>
    <div>
        <button @click="handleClick">
            <slot></slot>
        </button>
    </div>
</template>

<script>
    export default {
        name: 'zButton',
        data() {
            return {}
        },
        components: {},
        methods: {
            handleClick(event) {
                this.$emit('click', event)
                event.preventDefault()
            }
        },
    }
</script>

<style scoped>

</style>
