<template>
    <div class="selected-item">
        <ListItem v-if="selectedItem" :item="selectedItem"/>

        <div v-else>No selected item</div>
    </div>
</template>

<script>
import ListItem from '@/components/ListItem.vue';

export default {
    name: 'SelectedItem',

    components: {
        ListItem,
    },

    props: {
        item: {
            type: [Number, null],
            default: null,
        },

        items: {
            type: Array,
            default: () => [],
        },
    },

    computed: {
        selectedItem() {
            return this.items.find(item => item.id === this.item) || null;
        },
    },
}
</script>

<style lang="scss" scoped>
    .selected-item {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 500px;
        height: 300px;
        border: 1px solid #000;
    }
</style>