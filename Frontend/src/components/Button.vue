<template>
    <button class="button card-button">Подробнее</button>
</template>

<script>

</script>

<style lang="scss">
    .button {
        padding: 1rem 2rem;
        border-radius: 1.2rem;
        cursor: pointer;
    }

    .btn-try-free,
    .btn-buy {
        padding-inline: 2.5rem;
        font-size: 1.2rem;
        border: 2px solid $light;
        background: none;
        color: $gray;
        transition: 0.2s ease-in-out;

        &:hover {
            transform: translate(-4px, -4px);
            color: $light;
            border: 2px solid $gray;
        }
    }

    .card-button {
        position: absolute;
        bottom: 1.8rem;
        left: 2.5rem;
        border: none;
        font-size: 1rem;
        font-weight: 500;
        background-color: $accent-violet;
        color: $light;
        transition: 0.2s ease-in-out;

        &:hover {
            padding: 0.95rem 1.95rem;
            font-size: 0.95rem;
            background-color: $accent-violet-hover;
        }
    }

    .button-send {
        display: block;
        padding: 0.6rem 1.2rem;
        margin-top: 1rem;
        border: 2px solid $accent-violet;
        border-radius: 1rem;
        background-color: $accent-violet;
        color: $light;
        cursor: pointer;
        transition: 0.2s ease-in-out;

        &:hover {
            transform: translate(-2px, -2px);
            color: $light;
            border: 2px solid $gray;
        }
    }
</style>