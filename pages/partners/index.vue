<template>
  <div class="partner-list container">
    <PartnerTile v-for="(partner, idx) in partners" :key="idx" :partner="partner" />
  </div>
</template>

<script>
import content from '../../content.json'
import PartnerTile from '../../components/PartnerTile'

export default {
  name: 'Index',
  components: { PartnerTile },
  data: () => ({
    partners: content.partners
  })
}
</script>

<style scoped lang="scss">
  .partner-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }
</style>
