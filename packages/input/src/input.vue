<template>
    <div>
<!--        <input :type="type" :value="value" v-on="$listeners" v-bind="$attrs">-->
        <input :type="type" :value="value" @input="handleInput" v-bind="$attrs">
    </div>
</template>

<script>
    export default {
        name: 'zInput',
        data() {
            return {}
        },
        inheritAttrs: false,
        props: {
            type: {
                type: String,
                default: 'text'
            },
            value: {
                type: String
            }
        },
        components: {},
        methods: {
            handleInput(event) {
                this.$emit('input', event.target.value)
                const findParent = parent => {
                    while(parent) {
                        if (parent.$options.name === 'zFormItem') {
                            break
                        }else {
                            parent = parent.$parent
                        }
                    }
                    return parent
                }
                const parent = findParent(this.$parent)
                if (parent) {
                    parent.$emit('validate')
                }
            }
        },
    }
</script>

<style scoped>

</style>
