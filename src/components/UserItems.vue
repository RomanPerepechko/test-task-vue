<template>
    <div class="user-items">
        <ListItem
            :disabled="selectedItemsIds.includes(item.id)"
            v-for="item in items"
            :key="item.id"
            :item="item"
            @click.native="selectItem(item)"
        />
    </div>
</template>

<script>
import ListItem from '@/components/ListItem.vue';

export default {
    name: 'UserItems',

    components: {
        ListItem
    },

    props: {
        items: {
            type: Array,
            default: () => [],
        },

        value: {
            type: Array,
            default: () => [],
        },
    },

    methods: {
        selectItem(item) {
            if (this.selectedItemsIds.includes(item.id) || this.value.length >= 6) {
                return;
            }

            this.$emit('input', [...this.value, item]);
        },
    },

    computed: {
        selectedItemsIds() {
            return this.value.map(item => item.id);
        },
    },
}
</script>

<style lang="scss" scoped>
    .user-items {
        display: flex;
        flex-wrap: wrap;
        gap: 8px;
        width: 100%;
        padding: 16px;
        border: 1px solid #000;
        cursor: pointer;
    }
</style>