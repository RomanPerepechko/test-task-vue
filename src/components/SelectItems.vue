<template>
    <div class="select-items">
        <ListItem
            v-for="item in items"
            :key="item.id"
            :item="item"
            :disabled="value === item.id"
            @click.native="selectItem(item.id)"
        />
    </div>
</template>

<script>
import ListItem from '@/components/ListItem.vue';

export default {
    name: 'SelectItems',

    components: {
        ListItem,
    },

    props: {
        items: {
            type: Array,
            default: () => [],
        },

        value: {
            type: [Number, null],
            default: null,
        },
    },

    methods: {
        selectItem(id) {
            this.$emit('input', id);
        },
    },
}
</script>

<style lang="scss" scoped>
    .select-items {
        display: flex;
        flex-wrap: wrap;
        gap: 8px;
        width: 100%;
        padding: 16px;
        border: 1px solid #000;
    }
</style>