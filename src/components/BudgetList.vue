<template>
<div class="budget-list-wrap">
  <el-card :header="header">
    <template v-if="!isEmpty">
      <div class='list-item' v-for="(item, prop) in list" :key="prop">
        <budget-list-item :item="item" />
        <!-- <span class='budget-comment'>{{ item.comment }}</span>
        <span class='budget-value'>{{ item.value }}</span>
        <el-button type="danger" size="mini" @click="deleteItem(item.id)">Delete</el-button> -->
      </div>
    </template>
    <el-alert v-else type='info' :title="emptyTitle"/>
  </el-card>

</div>

</template>

<script>
import BudgetListItem from './BudgetListItem'

export default {
  name: 'BudjetList',
  components: {
    BudgetListItem
  },
  props: {
    list: {
      type: Object,
      default: () => ({}),
    }
  },
  data: () => ({
    header: "Budget List",
    emptyTitle: "List is empty"
  }),
  computed: {
    isEmpty() {
      return !Object.keys(this.list).length
    }
  }
}

</script>

<style scoped>
  .budget-list-wrap {
    width: 500px;
    margin: auto;
  }
  .list-item {
    display: flex;
    align-items: center;
    padding: 10px 15px;
  }
  .budget-value {
    font-weight: bold;
    margin-left: auto;
    margin-right: 20px;
  }
</style>