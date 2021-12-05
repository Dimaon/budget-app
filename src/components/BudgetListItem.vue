<template>
  <div>
    <span class='budget-comment'>{{ item.comment }}</span>
    <span class='budget-value'>{{ item.value }}</span>
    <el-button type="danger" size="mini" @click="deleteItem(item.id)">Delete</el-button>
  </div>
</template>

<script>
export default {
  name: 'BudgetListItem',
  props: {
    item: {
      type: Object,
      default: () => ({})
    }
  },
  methods: {
    deleteItem(id) {
      return this.$emit('onDeleteItem', id);
    }
  }
}
</script>

<style scoped>

</style>