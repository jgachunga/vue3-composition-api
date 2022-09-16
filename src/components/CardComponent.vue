<template>
    <div class="card">
        <slot name="header"></slot>
        <slot name="body"></slot>
        <slot name="footer"></slot>
    </div>
</template>

<script>
    export default {
        name: 'CardComponent',
        props: ['content'],
        data () {
            return  {
                
            }
        }
     }
</script>

<style lang="scss" scoped>
    .card {
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
        transition: 0.3s;
        padding: 16px;
        margin-bottom: 20px;
        width: 200px;
        &:hover {
            box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
        }
    }
</style>