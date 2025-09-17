<template>
    <div class="card bg-base-100 w-96 shadow-sm">
        <div class="card-body">
            <h2 class="card-title">Composant affichage des utilisateur</h2>
            <p>{{ user.name }}</p>
            <p>{{ user.age }}</p>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    user: {
        type: Object,
        required: true,
    },
});
</script>
