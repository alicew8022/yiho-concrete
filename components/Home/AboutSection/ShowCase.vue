<template>
  <div class="showcase">
    <div class="circle"></div>
    <div class="flex justify-start pad:justify-center pl-[55px] pad:pt-[106px] left-0 top-0 bottom-0 right-0 m-auto relative">
      <img src="/images/about.png" alt="first-image" class="first-image" />
      <SvgoDottedTexture class="dotted-texture-top" filled>
      </SvgoDottedTexture>
    </div>
    <!-- <div class="absolute left-0 bottom-0">
        <img src="/images/4.jpeg" alt="first-image" class="secondary-image" />
        <SvgoDottedTexture class="dotted-texture-bottom" filled></SvgoDottedTexture>
    </div> -->

  </div>
</template>

<style lang="scss" scoped>
.showcase {
  @apply relative w-full pad:aspect-square pad:overflow-hidden;
}

.first-image {
  @apply w-[290px] object-fill rounded-2xl;
  @screen pad {
    @apply w-[500px];
  }
  @screen desktop {
    @apply w-[700px];
  }
}

.dotted-texture-top {
  @apply hidden absolute top-[24px] -left-[39px] w-16 h-36;
}

.dotted-texture-bottom {
  @apply hidden absolute bottom-[28px] -left-[39px] w-16 h-36;
}

.circle {
  // @apply absolute right-0 w-[38%] h-[38%] border-[#E8382F] border-[30px] rounded-full;
  @apply absolute transition-all w-[6.75rem] h-[6.75rem] right-0 -top-[80px] z-0 pad:overflow-hidden bg-[url(~/assets/icons/half-circle.svg)] bg-no-repeat;
  
  @screen pad {
    @apply w-[29.5625rem] h-[29.5625rem];
  }
  @screen desktop {
    @apply w-[41.5625rem] h-[41.5625rem];
  }
  // &::before {
  //   content: '';
  //   @apply w-full h-full border-[1.875rem] bg-[url(~/assets/icons/half-circle.svg)] -translate-y-full pad:translate-x-1/3 pad:-translate-y-1/3 block;
  //   @screen pad {
  //     @apply bg-cover border-[3.75rem];
  //   }
  // }
}

</style>
