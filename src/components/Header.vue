<script setup>
    defineProps({
        totalPrice: Number 
    })

   const emit = defineEmits(['openDrawer'])
</script>

<template>
    <header class="flex justify-between border-b border-slate-100 px-10 py-8">

        <routerLink to="/">
            <div class="flex items-center gap-4">
                <img src="/logo.png" alt="Logo" class="w-10">
                <div>
                    <h2 class="text-xl font-bold uppercase">Vue Sneakers</h2>
                    <p class="text-slate-400">Магазин лучших кроссовок</p>
                </div>
            </div>
        </RouterLink>
        

        <ul class="flex items-center gap-10">
            <li @click="() => emit('openDrawer')" class="flex items-center cursor-pointer gap-3 text-gray-500 hover:text-black">
                <img src="/cart.svg" alt="">
                <b>{{ totalPrice }} руб.</b>
            </li>
            <routerLink to="/favorites">
                <li class="flex items-center cursor-pointer gap-3 text-gray-500 hover:text-black">
                    <img src="/heart.svg" alt="">
                    <span>Закладки</span>
                </li>
            </RouterLink>
            <li class="flex items-center cursor-pointer gap-3 text-gray-500 hover:text-black">
                <img src="/profile.svg" alt="">
                <span>Профиль</span>
            </li>
        </ul>
    </header>
</template>