<template>
    <footer>
        <p>Copyright &copy; 2023</p>
        <router-link to="/about">About</router-link>
    </footer>
</template>

<script>
export default {
    name: 'my-footer'
}
</script>

<style scoped>
a {
  color: #333;
}

footer {
  margin-top: 30px;
  text-align: center;
}
</style>