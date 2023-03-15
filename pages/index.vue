<template>
    <div class="container mx-auto w-1/2 py-8 divide-y space-y-8 divide-gray-100">
        <title>{{ title }}</title>
        <PostItem v-for="post in posts" :key="post.id" :post="post" />
    </div>
</template>
<script setup>
const title = useState('title')
// const { data: posts } = await useFetch('http://nuxt-3-blog-laravel.test/api/posts')

// const { data: posts } = await useFetch('/api/posts', {
//     baseURL: 'http://nuxt-3-blog-laravel.test'
// })

const posts = await useNuxtApp().$apiFetch('/api/posts')

</script>