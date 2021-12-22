<template>
    <div class="single-disc">
        <div class="disc-image">
            <img src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="Disc Album">
        </div>

        <div class="disc-title">
            <h3>New Jersey</h3>
        </div>

        <div class="disc-author">
            Bon Jovi
        </div>
    
        <div class="disc-year">
            1988
        </div>
    </div>
</template>


<script>
export default {
    name: 'SingleDisc'
}
</script>


<style scoped lang="scss">
@import '../style/variables';


.single-disc {
    background-color: $page-secondary-color;
    width: calc((100% / 5) - 40px);
    margin: 10px 20px;
    text-align: center;
    padding: 15px;

    .disc-title {
        text-transform: uppercase;
        color: white;
        font-size: 15px;
        margin: 15px 0;
    }

    .disc-author,
    .disc-year {
        color: #7e7c7b;
    }
}
</style>
