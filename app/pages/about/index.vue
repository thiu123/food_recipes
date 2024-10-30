<template>
  <div class="mx-20">
    <h1 class="text-5xl text-gray-900 my-5">About me</h1>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start">
      <!-- Cột nội dung -->
      <div>
        <div class="mb-3">
          <h2 class="text-3xl font-bold mb-1 text-gray-800">Who am I</h2>
          <p class="text-lg leading-relaxed">
            My name is Hieu, and I created this website for people who want to
            learn cooking but don't know where to start. Whether you're a
            complete beginner or someone looking to expand your culinary skills,
            this platform is designed to guide you step-by-step. With simple,
            easy-to-follow recipes, cooking tips, and a supportive community,
            you’ll be able to turn your kitchen into a space for creativity and
            joy. We believe that good food brings people together, and our goal
            is to make cooking accessible and enjoyable for everyone.
          </p>
        </div>
        <div class="mb-6">
          <h2 class="text-3xl font-bold mb-1 text-gray-800">My Mission</h2>
          <p class="text-lg leading-relaxed">
            With simple, easy-to-follow recipes, cooking tips, and a supportive
            community, my mission is to make cooking accessible and enjoyable
            for everyone. I believe that good food brings people together, and
            through this platform, I aim to inspire creativity and joy in every
            kitchen.
          </p>
        </div>
      </div>
      <!-- Cột hình ảnh -->
      <div class="flex justify-end">
        <NuxtImg src="/about_images.jpg"  class="h-full max-h-[500px] rounded-lg"/>
      </div>
    </div>
  </div>
</template>

<script setup></script>
