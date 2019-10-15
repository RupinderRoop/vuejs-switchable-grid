<template>
  <div>
    <ul class="list-group">
      <li class="list-group-item" v-for="el in data" :key="el.id">
        <div class="row">
          <div class="col-md-3">
            <img :src='el.thumbnailUrl' :alt="thumbnail">
          </div>
          <div class="col-md-9">
            {{ el.title }}
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ['data']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
