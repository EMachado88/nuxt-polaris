<template>
<router-link class="Polaris-Link" 
   :to="url" 
   :target="external ? '_blank' : ''"
   @click="onClick">
    <slot></slot>
</router-link>
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
