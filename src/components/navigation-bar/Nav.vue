<script setup>
import { reactive } from "vue";
import cartIcon from "@/components/svgs/icons/Cart.vue";
const navItems = reactive([
  { id: 1, title: "Collections", className: "nav-item", target: "/" },
  { id: 2, title: "Men", className: "nav-item", target: "/" },
  { id: 3, title: "Women", className: "nav-item", target: "/" },
  { id: 4, title: "About", className: "nav-item", target: "/" },
  { id: 5, title: "Contact", className: "nav-item", target: "/" },
]);
</script>
<template>
  <header class="flex justify-between container py-6 border-b border-solid border-b-slate-400 mb-10">
    <div class="header-left flex gap-x-7 items-center">
      <div class="logobar font-bold text-2xl font-serif">sneakers</div>
      <nav class="navbar">
        <ul class="nav-list flex gap-x-5">
          <li
            v-for="navItem in navItems"
            :key="navItem.id"
            :class="navItem.className"
          >
            <RouterLink :to="navItem.target">{{ navItem.title }}</RouterLink>
          </li>
        </ul>
      </nav>
    </div>
    <div class="header-right flex items-center gap-4">
      <div>
        <cartIcon className="fill-slate-600"/>
      </div>
      <div>
        <img src="@/assets/avatars/avatar-1.png" class="w-11" />
      </div>
    </div>
  </header>
</template>
<style scoped>
.nav-item {
  @apply text-slate-600 hover:text-black
}
</style>