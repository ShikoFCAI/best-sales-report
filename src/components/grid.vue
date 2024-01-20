<script setup>
import { ref, onMounted } from 'vue';
import CardSecondary from '@/components/card/secondary.vue'

const colors = ref([
    "orange",
    "cyan",
    "red",
    "green",
    "purple",
    "yellow",
])

let data = ref(null);

onMounted(async () => {
    const response = await fetch('https://fakestoreapi.com/products?limit=10');
    data.value = await response.json();
});
</script>

<template>
    <div class="grid">
        <div class="card" v-for="(entry, index) in data">
            <CardSecondary :entry="entry" :color="colors[(index) % colors.length]" class="" />
        </div>
    </div>
</template>

<style lang="scss" scoped>
@import '@/assets/style.scss';

.grid {
    @include flex-col(21px);

    @include lg {
        display: grid;
        grid-template-rows: repeat(2, minmax(0, 1fr));
        grid-template-columns: repeat(5, minmax(0, 1fr));
    }

    .card {
        @include max-card-width;
    }
}
</style>