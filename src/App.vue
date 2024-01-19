<script setup>
import MainCard from '@/components/card/main.vue'
import Grid from '@/components/grid.vue'
</script>

<template>
    <div class="main">
        <MainCard />
        <Grid />
    </div>
</template>

<style lang="scss" scoped>
.main {
    @import '@/assets/style.scss';

    @include flex-col(40px);

    padding: 81px 24px;
    @include lg {
        padding: 0;
        @include flex-row(33px);
    }
}
</style>
