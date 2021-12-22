<template>
    <div class="single-disc">
        <div class="disc-image">
            <img :src="objectDisc.poster" :alt="objectDisc.title">
        </div>

        <div class="disc-title">
            <h3>{{ objectDisc.title }}</h3>
        </div>

        <div class="disc-author">
            {{ objectDisc.author }}
        </div>
    
        <div class="disc-year">
            {{ objectDisc.year }}
        </div>
    </div>
</template>


<script>
export default {
    name: 'SingleDisc',
    props: {
        objectDisc: Object
    }
}
</script>


<style scoped lang="scss">
@import '../style/variables';


.single-disc {
    background-color: $page-secondary-color;
    width: calc((100% / 5) - 40px);
    margin: 10px 20px;
    height: 300px;
    text-align: center;
    padding: 15px;
    cursor: pointer;

    .disc-title {
        text-transform: uppercase;
        color: white;
        font-size: 15px;
        margin: 15px 0;
    }

    .disc-year {
        font-size: 13px;
    }

    .disc-author,
    .disc-year {
        color: #7e7c7b;
    }
}
</style>
