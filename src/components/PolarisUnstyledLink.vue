<template>
<router-link :to="url" 
   :target="external ? '_blank' : ''"
   :rel="external ? 'noopener noreferrer' : ''"
   data-polaris-unstyled="true">
    <slot></slot>
</router-link>
</template>

<script>
export default {
    props: {
        url: String,
        external: Boolean,
    }
}
</script>
