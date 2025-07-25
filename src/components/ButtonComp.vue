<template>
    <button class="btn" @click="$emit('click')">{{ label }}</button>
</template>
<script>
export default {
    name: 'ButtonComp',
    props: {
        label: String,
        color: String,
    },
    computed: {
        backgroundColor() {
            if (this.color === 'blue') return '#28a745';
            if (this.color === 'yellow') return '#ffc107';
            return '#007bff';
        },
        textColor() {
            return this.color === 'yellow' ? 'black' : 'white';
        }
    }
}
</script>
<style>
</style>