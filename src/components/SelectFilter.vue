<template>
    <div class="select-filter">
        <select @change="$emit('selectClicked', selectText)" v-model="selectText" name="" id="">
            <option value="">All</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
            <option value="Rap">Rap</option>
        </select>
    </div>
</template>


<script>
export default {
    name: 'SelectFilter',
    data: function() {
        return {
            selectText: ''
        }
    }
}
</script>


<style lang="scss" scoped>
.select-filter {
    select {
        width: 200px;
        margin-left: 20px;
    }
}
</style>