<script setup lang="ts">

definePageMeta({
    middleware: 'auth'
})

const { signOut } = useAuth();

const submitLogout = ()=>{
    signOut({redirect: false}).then(()=>{
                console.log("Sucessfully logout!")
                navigateTo('/');
            })
            .catch((error)=>{
                console.log("Error when trying to logout: ", error);
            });
}
</script>

<template>
    <div>
        <h1>Minha Tela Home!!</h1>
        <button @click="submitLogout" class="customButton">SAIR</button>
    </div>
</template>

<style lang="scss">

</style>