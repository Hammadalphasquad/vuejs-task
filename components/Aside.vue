<template>
  <div
    class="max-w-[260px] w-full h-[833px] text-[#717D96] bg-[#EDF0F7] border-[#1A202C] border-r-2 py-6"
  >
    <div class="flex items-center py-3 pl-10 gap-2.5 cursor-pointer">
      <img src="/images/icon-placeholder.png" alt="" />
      <p class="text-sm leading-6 font-medium">Products</p>
    </div>
    <div
      @click="isSettingsOpen = !isSettingsOpen"
      class="flex items-center py-3 hover:bg-[#E2E7F0] pl-10 gap-[10px] hover:text-[#2D3648] cursor-pointer"
    >
      <svg
        width="16"
        height="16"
        viewBox="0 0 16 16"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M3.3335 1.3335C2.80306 1.3335 2.29436 1.54421 1.91928 1.91928C1.54421 2.29436 1.3335 2.80306 1.3335 3.3335V5.3335C1.3335 5.70169 1.63197 6.00016 2.00016 6.00016C2.36835 6.00016 2.66683 5.70169 2.66683 5.3335V3.3335C2.66683 3.15668 2.73707 2.98712 2.86209 2.86209C2.98712 2.73707 3.15668 2.66683 3.3335 2.66683H5.3335C5.70169 2.66683 6.00016 2.36835 6.00016 2.00016C6.00016 1.63197 5.70169 1.3335 5.3335 1.3335H3.3335Z"
          fill="#2D3648"
        />
        <path
          d="M10.6668 1.3335C10.2986 1.3335 10.0002 1.63197 10.0002 2.00016C10.0002 2.36835 10.2986 2.66683 10.6668 2.66683H12.6668C12.8436 2.66683 13.0132 2.73707 13.1382 2.86209C13.2633 2.98712 13.3335 3.15669 13.3335 3.3335V5.3335C13.3335 5.70169 13.632 6.00016 14.0002 6.00016C14.3684 6.00016 14.6668 5.70169 14.6668 5.3335V3.3335C14.6668 2.80306 14.4561 2.29436 14.081 1.91928C13.706 1.54421 13.1973 1.3335 12.6668 1.3335H10.6668Z"
          fill="#2D3648"
        />
        <path
          d="M2.66683 10.6668C2.66683 10.2986 2.36835 10.0002 2.00016 10.0002C1.63197 10.0002 1.3335 10.2986 1.3335 10.6668V12.6668C1.3335 13.1973 1.54421 13.706 1.91928 14.081C2.29436 14.4561 2.80306 14.6668 3.3335 14.6668H5.3335C5.70169 14.6668 6.00016 14.3684 6.00016 14.0002C6.00016 13.632 5.70169 13.3335 5.3335 13.3335H3.3335C3.15669 13.3335 2.98712 13.2633 2.86209 13.1382C2.73707 13.0132 2.66683 12.8436 2.66683 12.6668V10.6668Z"
          fill="#2D3648"
        />
        <path
          d="M14.6668 10.6668C14.6668 10.2986 14.3684 10.0002 14.0002 10.0002C13.632 10.0002 13.3335 10.2986 13.3335 10.6668V12.6668C13.3335 12.8436 13.2633 13.0132 13.1382 13.1382C13.0132 13.2633 12.8436 13.3335 12.6668 13.3335H10.6668C10.2986 13.3335 10.0002 13.632 10.0002 14.0002C10.0002 14.3684 10.2986 14.6668 10.6668 14.6668H12.6668C13.1973 14.6668 13.706 14.4561 14.081 14.081C14.4561 13.706 14.6668 13.1973 14.6668 12.6668V10.6668Z"
          fill="#2D3648"
        />
      </svg>

      <p class="text-sm leading-6 font-medium">Settings</p>
      <i class="fa"></i>
    </div>
    <div v-if="isSettingsOpen" class="flip-in-hor-bottom">
      <ul>
        <NuxtLink
          to="/categories"
          exact-active-class="bg-[#D4D8DF]"
          class="hover:bg-[#D4D8DF] flex py-1.5 leading-6 text-sm font-medium pl-[67px] cursor-pointer"
        >
          Categories
        </NuxtLink>
        <NuxtLink
          to="/product-type"
          exact-active-class="bg-[#D4D8DF]"
          class="hover:bg-[#D4D8DF] flex py-[6px] leading-6 text-sm font-medium pl-[67px] cursor-pointer"
        >
          Product Type
        </NuxtLink>
        <NuxtLink
          to="/product-size"
          exact-active-class="bg-[#D4D8DF]"
          class="hover:bg-[#D4D8DF] flex py-[6px] leading-6 text-sm font-medium pl-[67px] cursor-pointer"
        >
          Product Size
        </NuxtLink>
        <NuxtLink
          to="/attributes"
          exact-active-class="bg-[#D4D8DF]"
          class="hover:bg-[#D4D8DF] flex py-[6px] leading-6 text-sm font-medium pl-[67px] cursor-pointer"
        >
          Attributes
        </NuxtLink>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const isSettingsOpen = ref(false);

const inputs = ref([
  { value: "Print Only" },
  { value: "Print and Mail" },
  { value: "Electronic" },
]);

const addInput = () => {
  inputs.value.push({ value: "" });
};

const removeInput = (index) => {
  inputs.value.splice(index, 1);
};
</script>
