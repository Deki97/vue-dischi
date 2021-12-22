<template>
    <header>
        <div class="logo">
            <img src="../assets/img/spotify-logo.png" alt="Spotify Logo">
        </div>
    </header>
</template>


<script>
export default {
    name: 'Header'
}
</script>


<style scoped lang="scss">
@import '../style/variables';

header {
    padding: 10px 30px;
    background-color: $page-secondary-color;

    .logo {
        img {
            width: 50px;
        }
    }
}
</style>
