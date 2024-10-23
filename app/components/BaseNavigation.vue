<template>
  <div>
    <header class="py-4 border-b">
      <nav class="flex justify-between mx-20 items-center">
        <nuxt-link to="/" class="flex items-center gap-1">
          <NuxtImg
            src="/recipes_avt.png"
            alt="Food Recipes Logo"
            class="w-6 h-6"
          />
          <span class="lg:text-2xl text-xl mr-10">Food Recipes</span>
        </nuxt-link>
        <ul class="flex gap-6">
          <li>
            <nuxt-link to="/" class="lg:text-2xl text-xl">Home</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/about" class="lg:text-2xl text-xl">About</nuxt-link>
          </li>
        </ul>
      </nav>
    </header>
  </div>
</template>
