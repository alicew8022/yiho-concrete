<template>
  <section class="section">
    <h2 class="section-title">工程實績</h2>
    <div class="section-content">
      <SectionSubtitle title="全方位建築最佳選擇"></SectionSubtitle>
      <div class="showcases relative" v-drag-scroller>
        <div class="circle-bg flex justify-center items-center">
          <CircleAnimation v-if="breakpoint.lg.value" ></CircleAnimation>
        </div>
        <HomeAchievementSectionShowCase v-for="item in galleryList" :title="item.name" :image="`/files/achievements/${item.image}`"></HomeAchievementSectionShowCase>
      </div>
    </div>
  </section>
</template>
<script setup lang="ts">
import useApp from '~/hooks/useApp';

const { breakpoint } = useApp();
const { $trpcClient } = useNuxtApp()

const { data, execute, refresh } = await $trpcClient.getTop4Gallery.useQuery()

const galleryList = computed(() => {
  return data.value?.map((item) => {
    return {
      name: item.name,
      image: item.images.find(image => image.is_cover)?.file
    }
  })
})

</script>
<style lang="scss" scoped>

.section {
  @apply px-6;
  
  @screen pad {
    @apply px-[1.875rem];
  }
  @screen desktop {
    @apply px-[2.8125rem];
  }
}

.section-title {
  font-size: 1.5rem;;
  margin-bottom: .75rem
}

.section-content {
  &-subtitle {
    display: flex;
    align-items: center;
  }
}

.showcases {
  @apply flex gap-6 overflow-hidden;

  @screen pad {
    @apply grid grid-cols-2
  }

  // display: grid;
  // width: 100%;
  // grid-template-columns: repeat(2, 1fr);
  // gap: 1.5rem;
  // // background-image: url('~/assets/icons/bg-circle.svg');
  // background-repeat: no-repeat;
  // background-position: center center;
  // position: relative;
}

.circle-bg {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  margin: auto;
  width: 80%;
  height: 80%;
  z-index: -1;
}

</style>