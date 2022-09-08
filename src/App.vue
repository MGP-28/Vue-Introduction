<script lang="js">
import ContentContainer from './components/ContentContainer.vue';

export default {
    components: { ContentContainer }
}
</script>

<template>
  <div class="container">
    <ContentContainer></ContentContainer>
  </div>
</template>

<style scoped>
.container{
  display: flex;
  flex-direction: column;
  gap: 20px;
  max-width: 800px;
}
</style>
