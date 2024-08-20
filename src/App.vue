<template>
  <div class="main-page">
    <div class="main-page__header">
      <UserSelectedItems :selected-items="userSelectedItems" :items="userItemsList"/>

      <SelectedItem :item="selectedItem" :items="selectItemsList"/>
    </div>

    <div class="main-page__wrapper">
      <UserItems
        class="main-page__item"
        :items="userItemsList"
        v-model="userSelectedItems"
      />

      <SelectItems
        class="main-page__item"
        :items="selectItemsList"
        v-model="selectedItem"
      />
    </div>
  </div>
</template>

<script>
import UserSelectedItems from '@/components/UserSelectedItems.vue';
import SelectedItem from '@/components/SelectedItem.vue';
import SelectItems from '@/components/SelectItems.vue';
import UserItems from '@/components/UserItems.vue';


export default {
  name: 'MainPage',

  components: {
    SelectItems,
    UserItems,
    SelectedItem,
    UserSelectedItems,
  },

  data() {
    return {
      userItemsList: [
        {
          "id": 1,
          "name": "Shoes 1"
        },
        {
            "id": 2,
            "name": "Shoes 2"
        },
        {
            "id": 3,
            "name": "Shoes 3"
        },
        {
            "id": 4,
            "name": "Shoes 4"
        },
        {
            "id": 5,
            "name": "T-shirt 1"
        },
        {
            "id": 6,
            "name": "T-shirt 2"
        },
        {
            "id": 7,
            "name": "T-shirt 3"
        },
        {
            "id": 8,
            "name": "T-shirt 4"
        }
      ],
      selectItemsList: [
        {
          "id": 11,
          "name": "Jacket 1"
        },
        {
            "id": 12,
            "name": "Jacket 2"
        },
        {
            "id": 13,
            "name": "Jacket 3"
        },
        {
            "id": 14,
            "name": "Jacket 4"
        },
        {
            "id": 15,
            "name": "Hoodie 1"
        },
        {
            "id": 16,
            "name": "Hoodie 2"
        },
        {
            "id": 17,
            "name": "Hoodie 3"
        },
        {
            "id": 18,
            "name": "Hoodie 4"
        }
      ],

      selectedItem: null,
      userSelectedItems: [],
    }
  },
}
</script>

<style lang="scss">
body, html {
  margin: 0;
}

.main-page {
  width: 100%;
  padding: 32px;

  &__header {
    display: flex;
    column-gap: 16px;
    justify-content: space-between;
    margin-bottom: 32px;
  }

  &__wrapper {
    display: flex;
    column-gap: 16px;
  }

  &__item {
    flex: 1;
  }
}
</style>
