<template>
    <article class="service-card">
        <img class="img-custom" 
             :src="path"
             alt="Girl lacing sneakers">
        <h3 class="card-title">{{ title }}</h3>
        <slot></slot>
    </article>
</template>

<script setup>
    defineProps({
        title: String,
        path: String
    });
</script>

<style lang="scss" scoped>
    .service-card {
        position: relative;
        height: 400px;
        border-radius: 1.5rem;
        transition: all 0.2s ease-in-out;

        &:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 12px rgba(0, 0, 0, 0.3);
        }
    }

    .img-custom {
        width: 100%;
        height: 100%;
        border-radius: 1.5rem;
        object-fit: cover;
    }

    .card-title {
        position: absolute;
        top: 1.8rem;
        left: 2.5rem;
        font-size: 1.5rem;
        font-weight: 500;
        color: $light;
        text-shadow: 1px 4px 5px rgba(0, 0, 0, 0.7);
    }
</style>