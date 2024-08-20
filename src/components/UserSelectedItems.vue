<template>
    <div class="user-selected">
        <template v-if="selectedItems.length">
            <ListItem
                v-for="item in selectedItems"
                :key="item.id"
                :item="item"
            />
        </template>
        
        <span v-else>
            No selected items
        </span>
    </div>
</template>
<script>
import ListItem from '@/components/ListItem.vue';

export default {
    name: 'UserSelectedItems',

    components: {
        ListItem,
    },

    props: {
        selectedItems: {
            type: Array,
            default: () => [],
        },
    },
}
</script>
<style lang="scss" scoped>
    .user-selected {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 16px;
        flex-wrap: wrap;
        padding: 16px;
        width: 500px;
        height: 300px;
        border: 1px solid #000;
    }
</style>