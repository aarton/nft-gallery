<template>
  <div class="columns is-multiline">
    <div
      class="column is-one-quarter-desktop is-one-third-tablet"
      v-for="nft in items"
      :key="nft.id"
    >
      <GalleryCard :id="nft.id" :name="nft.name" :image="nft.image" />
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue, Watch } from 'vue-property-decorator';
import GalleryCard from './GalleryCard.vue';
import { RmrkType } from '@/components/rmrk/service/RmrkService';

const components = { GalleryCard };

@Component({ components })
export default class GalleryCardList extends Vue {
  @Prop() public items!: RmrkType[];
}
</script>
