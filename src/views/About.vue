<template>
    <p>Version 1.0</p>
    <router-link to="/">Go back</router-link>
    <!-- <div v-show="showAddTask"></div> -->
</template>

<script>
export default {
    name: 'my-about',
    props: ['showAddTask'],
}
</script>