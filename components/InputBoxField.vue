<template>
    <div>
        {{label}}
        <input :type="inputType" :placeholder="placeholder" :required="required" @input="$emit('changeInput', inputValue)" v-model="inputValue" />
    </div>
</template>

<script>

export default({
    name: 'InputBoxField',
    props: {
        label: {
            type: String,
            required: true
        },
        placeholder: {
            type: String,
            required: true
        },
        required: {
            type: String,
            required: true
        },
        inputType: {
            type: String,
            required: true
        },
    },
    data() {
        return {
        inputValue: ''
        }
    }
})
</script>
