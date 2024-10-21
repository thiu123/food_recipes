<template>
  <div>
    <section class="bg-[#f1f1f1]">
      <div class="flex mx-20">
        <div class="flex-col">
          <h1 class="text-6xl  font-extrabold mb-6 text-balance">
            Good food is the foundation of genuine happiness.
          </h1>
          <p class="text-2xl  mb-8 text-balance">
            Discover the secret to happiness, it’s in the recipe.
          </p>
          <button
            class="bg-dodgeroll-gold cursor-pointer rounded-md p-1 text-lg"
          >
            Browse Recipes
          </button>
        </div>
        <div>
          <NuxtImg src="/food_homepages.jpg" alt="Introduce recipes image"/>
        </div>
      </div>
    </section>

    <section>
      <div class="mx-20">
        <h1 class="text-4xl mt-7">Discover our favorites recipes</h1>
        <p>
          Ready to dive into the world of deliciousness? Below, you'll find a
          collection of handpicked recipes that promise to bring joy to your
          kitchen and happiness to your table.
        </p>
      </div>
      <div class="grid grid-cols-3 gap-7 mx-20">
        <div
          v-for="recipe in products.recipes"
          :key="recipe.id"
          class="flex flex-col shadow rounded-md"
        >
          <NuxtImg
            :src="recipe.image"
            alt="Recipe Image"
            class="rounded-t-md"
          />
          <div>
            <p class="text-xl mb-2">{{ recipe.name }}</p>
            <div class="flex text-lg w-full gap-7">
              <div class="flex items-center gap-1">
                <Icon
                  name="mdi:clock-time-eight-outline"
                  style="color: #f79f1a"
                />
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
          </div>
          <NuxtLink
            :to="`/recipes/${recipe.id}`"
            class="px-4 py-2 mt-2 text-white self-start bg-dodgeroll-gold rounded-md text-base lg:text-lg cursor-pointer"
          >
            View
          </NuxtLink>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
const { data: products } = await useFetch("https://dummyjson.com/recipes");
// console.log(products);
useSeoMeta({
  title: 'Food Recipes',
})
</script>
