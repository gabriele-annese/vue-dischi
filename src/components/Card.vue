<template>
        <div class="text-card mt-2">
            <h3 class="text-uppercase title">
                {{title}}
            </h3>
            <h4 class="author">
                {{subTitle}}
            </h4>
            <span class="year">
                {{year}}
            </span>
            <span class="genre d-block fs-5">
                {{Text}}
            </span>
        </div>
</template>

<script>
export default {
name: 'Card',
props:{
    img: String,
    title: String,
    subTitle: String,
    year: String,
    Text: String
}
}
</script>

<style lang="scss" scoped>
.year,
.author{
    color: lightgrey;
}
</style>