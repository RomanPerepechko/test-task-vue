<template>
    <div class="list-item" :class="{ '_disabled': disabled }">
        {{ item.name }}
    </div>
</template>

<script>
export default {
    name: 'ListItem',

    props: {
        item: {
            type: Object,
            default: () => ({}),
        },

        disabled: {
            type: Boolean,
            default: false,
        },
    },
}
</script>

<style lang="scss" scoped>
    .list-item {
        width: fit-content;
        height: fit-content;
        white-space: nowrap;
        padding: 8px 16px;
        border: 1px solid #000;
        cursor: pointer;

        &._disabled {
            cursor: not-allowed;
            opacity: .5;
        }
    }
</style>