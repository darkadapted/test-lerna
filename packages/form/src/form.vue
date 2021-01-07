<template>
    <form
       class="z-form"
       ref="z-form"
       :model="model"
       :rules="rules"
    >
        <slot />
    </form>
</template>

<script>
    export default {
        name: 'zForm',
        props: {
            model: {
                type: Object
            },
            rules: {
                type: Object
            }
        },
        provide() {
          return {
              form: this
          }
        },
        data() {
            return {}
        },
        components: {},
        methods: {},
    }
</script>

<style scoped>

</style>
