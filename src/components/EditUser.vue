<template>
    <div class="card bg-base-100 w-96 shadow-sm">
        <div class="card-body">
            <h2 class="card-title">Composant formulaire d'édition</h2>
            <label class="label">Votre nom</label>
            <input
                type="text"
                class="input"
                placeholder="Entrez votre nom"
                v-model="nameUser"
            />
            <label class="label">Votre âge</label>
            <input
                type="number"
                class="input"
                placeholder="Entrez votre âge"
                v-model.number="ageUser"
            />
            <button @click="emitModify" class="btn btn-primary">
                Mettre à jour
            </button>
        </div>
    </div>
</template>

<script setup>
import { ref, defineEmits } from "vue";
const emit = defineEmits(["modify"]);

const nameUser = ref("");
const ageUser = ref();

function emitModify() {
    if (!nameUser.value.trim()) {
        alert("Le nom est requis !");
        return;
    }
    if (!ageUser.value || ageUser.value <= 0) {
        alert("Âge invalide !");
        return;
    }
    emit("modify", { name: nameUser.value, age: ageUser.value });
}
</script>
