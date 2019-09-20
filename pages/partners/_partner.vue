<template>
  <div>
    <ImageBlock
      :title="partner.name"
      :image="partner.logoUrl"
      :type="'image-right'"
      :text="''"
    />
    <TextBlock
      :type="'text-left'"
      :text="partner.description"
      :contained="true"
      :button="{
        'url': partner.url,
        'text': 'Ga naar de website'
      }"
    />
  </div>
</template>

<script>
import content from '../../content.json'
import TextBlock from '../../components/TextBlock'
import ImageBlock from '../../components/ImageBlock'

export default {
  name: 'Partner',
  components: { ImageBlock, TextBlock },
  data: () => ({
    partner: {}
  }),
  validate({ params }) {
    return content.partners.some(partner => partner.slug === params.partner)
  },
  mounted() {
    const pageData = content.partners.find(p => p.slug === this.$route.params.partner)
    this.$set(this, 'partner', pageData)
  }
}
</script>

<style scoped>

</style>
