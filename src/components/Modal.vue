<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{sale: theme === 'sale'}">
            <slot></slot>
        </div>
    </div>
</template>

<script>
export default {
    props: ['warning', 'content', 'theme', 'header'],
    methods: {
        closeModal() {
            this.$emit('close')
        }
    }
}
</script>

<style>
    .modal{
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: white;
        border-radius: 10px;
    }

    .backdrop{
        top: 0;
        position: fixed;
        background: rgba(0, 0, 0, 0.5);
        width: 100%;
        height: 100%;
    }

    .modal p{
        font-style: normal; 
    }

    .modal.sale{
        background: teal;
        color: aliceblue;
    }
    .modal.sale.p{
        color: white;
    }
</style>