<script setup>
    const course = useCourse();
    const route = useRoute();

    const chapter = computed(() => {
        return course.chapters.find(
            (chapter) => chapter.slug === route.params.chapterSlug
        )
    })

    const lesson = computed(() => {
        return chapter.value.lessons.find(
            (lesson) => lesson.slug === route.params.lessonSlug
        )
    })
</script>
<template>
    <h2>Lesson</h2>
    <p>This is a lesson</p>
    <ul>
        <li>{{ chapter.title }}</li>
        <li>{{ lesson.title }}</li>
    </ul>
</template>