<template>
    <main>
        <div class="container">
            Ciao sono il main

            <SingleDisc />
        </div>
    </main>
</template>


<script>
import SingleDisc from "./SingleDisc.vue";

export default {
    name: 'Main',
    components: {
        SingleDisc
    }
}
</script>


<style scoped lang="scss">

</style>
