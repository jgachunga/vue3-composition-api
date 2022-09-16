<template>
    <div>
        <input type="text" name="" id="" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)">
    </div>
</template>

<script>
    export default {
        name: 'InputComponent',
        props:['modelValue'],
        emits: ['update:modelValue']
    }
</script>

<style lang="scss" scoped>
    input[type='text'] {
        display: block;
        width : 400px;
        padding: 6px 12px;
        font-size: 14px;
        line-height: 1.4;
        color: #555;
        background-color: #fff;
        border: 1px solid #ccc;
        border-radius: 4px;
    }
</style>