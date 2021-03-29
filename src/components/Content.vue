<template>
  <div class="page__content">
    <h2 class="page__content__heading">Дайджест показателей отделения</h2>

    <div class="page__content__widget-wrapper">
        <Widget/>
        <Widget/>
    </div>

    <div class="page__content__table-wrapper">
      <Table/>
    </div>
  </div>
</template>

<script>
import Widget from './internalContent/Widget.vue';
import Table from './internalContent/Table.vue';

export default {
  name: 'Content',
  components: {
    Widget,
    Table
  }
}
</script>

<style lang="scss" scoped>
.page__content{
    display: flex;
    flex-direction: column;
    width: 1360px;
    padding: 60px 51px 0;

    &__heading{
        font-size: 22px;
        color: rgba(32, 33, 36, 0.72);
        margin: 24px 0 32px;
    }

    &__widget-wrapper{
        display: flex;
        justify-content: space-between;
    }
}
</style>
