<script setup>

defineProps({
    buttonlink: {
        type: String,
        required: true
    }
})
</script>
<template>
    <div class="item">
        <a :href="'https://' + buttonlink + '/'">
            <i>
                <slot name="icon"></slot>
            </i>
        </a>
    </div>
</template>

<style scoped>
.item {
    margin-top: 2rem;
    display: flex;
    cursor: pointer;
}

.details {
    flex: 1;
    margin-left: 1rem;
}

i {
    display: flex;
    place-items: center;
    place-content: center;
    width: 50px;
    height: 50px;

    color: var(--color-text);
}

h3 {
    font-size: 1.2rem;
    font-weight: 500;
    margin-bottom: 0.4rem;
    color: var(--color-heading);
}

@media (min-width: 1024px) {
    .item {
        padding: 3rem 0 1rem calc(var(--section-gap) / 2);
    }

    i {
top: calc(50% - 40px);
    left: -40px;
    position: absolute;
    border-radius: 8px;
    width: 80px;
    height: 80px;
    }

    .item:before {
        content: " ";
        border-left: 1px solid var(--color-border);
        position: absolute;
        left: 0;
        bottom: calc(50% + 25px);
        height: calc(50% - 25px);
    }

    .item:after {
        content: " ";
        border-left: 1px solid var(--color-border);
        position: absolute;
        left: 0;
        top: calc(50% + 25px);
        height: calc(50% - 25px);
    }

    .item:first-of-type:before {
        display: none;
    }

    .item:last-of-type:after {
        display: none;
    }
}
</style>
