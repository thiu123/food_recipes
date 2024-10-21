<template>
  <div class="flex flex-col items-center  min-h-screen  bg-gray-50">
    <!-- Đảm bảo div chính chiếm toàn bộ chiều cao màn hình -->
    <div>
      <h1 class="text-3xl md:text-4xl font-bold text-gray-800 mb-4">{{ recipe.name }}</h1>
    </div>

     <div class="flex text-lg w-full gap-7 justify-center mb-3">
      <div class="flex items-center gap-1">
        <Icon name="mdi:clock-time-eight-outline" style="color: #f79f1a" />
        <span>{{ recipe.cookTimeMinutes }}</span>
      </div>
      <div class="flex items-center gap-1">
        <Icon name="mdi:fire" style="color: #f79f1a" />
        <span>{{ recipe.caloriesPerServing }}</span>
      </div>
      <div class="flex items-center gap-1">
        <Icon name="mdi:star" style="color: #f79f1a" />
        <span>{{ recipe.rating }} ({{ recipe.reviewCount }})</span>
      </div>
    </div>

    <!-- Image  -->
    <div class="w-full md:w-3/4 lg:w-1/2 flex justify-center mb-8">
      <NuxtImg
        :src="recipe.image"
        alt="Recipe Image"
        sizes="xs:100vw sm:100vw md:100vw lg:100vw"
        class="w-full max-h-[500px] object-cover rounded-md shadow-lg"
      />
    </div>

    <!-- Ingredient -->
    <div class="w-full md:w-3/4 lg:w-1/2">
      <h2 class="text-2xl font-semibold mb-4 text-gray-800">Ingredients</h2>
      <ul class="grid grid-cols-1 sm:grid-cols-2 gap-3 text-lg text-gray-700">
        <li
          v-for="(ingredient, index) in recipe.ingredients"
          :key="index"
          class="flex items-center"
        >
          <input type="checkbox" class="mr-2 h-4 w-4" />
          <span>{{ ingredient }}</span>
        </li>
      </ul>
    </div>

    <!-- Instruction -->
    <div class="w-full md:w-3/4 lg:w-1/2 mt-8">
      <h2 class="text-2xl font-medium mb-4 text-gray-800">Instructions</h2>
      <ul class="list-none text-lg text-gray-700 space-y-4">
        <li
          v-for="(instruction, index) in recipe.instructions"
          :key="index"
          class="flex items-start"
        >
          <span class="font-bold mr-2">{{ index + 1 }}.</span>
          <span>{{ instruction }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
const { id } = useRoute().params;
const uri_id = "https://dummyjson.com/recipes/" + id;
const { data: recipe } = await useFetch(uri_id);

useSeoMeta({
  title: recipe.value.name,
  description: 'Recipes for ' + recipe.value.name,
  ogTitle: recipe.value.name,
  ogDescription: 'Recipes for ' + recipe.value.name,
  ogImage: recipe.value.image,
  ogUrl: `localhost:3000/recipes/${recipe.value.id}`,
  twitterTitle: recipe.value.name,
  twitterDescription: 'Recipes for ' + recipe.value.name,
  twitterImage: recipe.value.image,
  twitterCard: 'summary'
})

console.log(recipe)
</script>
