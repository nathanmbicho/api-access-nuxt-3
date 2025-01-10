<script setup lang="ts">
  const { chapters } = useCourse();
</script>
<template>
    <div class="prose mb-12">
      <h1>
        <span class="font-medium">
          Course:
          <span class="font-bold">Mastering Nuxt 3</span>
        </span>
      </h1>
    </div>

    <div class="flex flex-row justify-center flex-grow">
      <div class="prose mr-4 p-8 bg-white rounded-md min-w-[20ch] max-w-[30ch] flex flex-col">
        <h3>Chapters</h3>
        <div class="space-y-1 mb-4 flex flex-col"
            v-for="(chapter, index) in chapters"
            :key="index"
          >
          <h4>{{ chapter.title }}</h4>
          <NuxtLink v-for="(lesson, index) in chapter.lessons" :key="index"
              :to="lesson.path"
              class="flex flex-row space-x-1 no-underline prose-sm font-normal py-1"
              :class="lesson.path === $route.fullPath  ? 'text-blue-500' : 'text-gray-600'"
            >
              <span class="text-gray-500">{{ index + 1 }}</span>
              <span>{{ lesson.title }}</span>
          </NuxtLink>
        </div>
      </div>

      <div class="prose p-12 bg-white rounded-md max-w-[73ch]">
        <NuxtPage />
      </div>
    </div>
</template>
