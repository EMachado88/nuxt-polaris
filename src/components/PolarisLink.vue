<template>
<a class="Polaris-Link" 
   :to="url" 
   :target="external ? '_blank' : ''"
   @click="onClick">
    <slot></slot>
</a>
</template>

<script>
export default {
    props: {
        url: String,
        external: Boolean
    },
    methods: {
        onClick(e) {
            this.$emit('click', e);
        }
    }
};
</script>
