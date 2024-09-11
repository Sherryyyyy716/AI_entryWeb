<template>
  <div class="footer bg-[#0A2F5A] text-center p-10 m-1 flex-col justify-center h-fit">
    <i>
      <slot name="icon"></slot>
    </i>
    <div class="details flex-col justify-center">
      <h3 class="text-3xl italic font-medium mb-8 mt-4 text-white text-left">
        <slot name="heading"></slot>
      </h3>
      <p class="text-white"><slot></slot></p>

      <el-button
        class="bg-white text-[#1A334B] px-24 sm:px-36 py-6 my-8 hover:bg-[#3E84BA] hover:text-white rounded-none border-0"
      >
        <slot name="btn"></slot>
      </el-button>
    </div>
  </div>
</template>

<style scoped></style>
