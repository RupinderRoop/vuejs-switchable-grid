<template>
  <div>
    <div class="row">
      <div v-for="el in data" :key="el.id">
          <div class="card">
            <img class="card-img" :src="el.thumbnailUrl" :alt="thumbnail">
            <div class="card-img-overlay">
              <h5 class="card-title">{{ el.title }}</h5>
            </div>
          </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['data']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.card {
  margin: 0 14px 15px;
}
.card-img {
  padding: 10px;
  height: 255px;
  width: 255px;
}
</style>
