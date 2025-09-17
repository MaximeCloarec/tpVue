<template>
    <div class="card bg-base-100 w-96 shadow-sm">
        <div class="card-body">
            <h2 class="card-title">Composant Gestion de l'utilisateur</h2>
            <ShowUser :user="user" />
            <EditUser v-on:modify="modifyUser($event)" />
        </div>
    </div>
</template>

<script setup>
import { ref } from "vue";
import ShowUser from "./components/ShowUser.vue";
import EditUser from "./components/EditUser.vue";

const user = ref({
    name: "Jhon",
    age: 25,
});

function modifyUser(newUser) {
    user.value = newUser;
}
</script>
