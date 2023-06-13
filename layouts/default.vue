<script>

export default {
    data() {
        return {
            'navitems': [
                {
                    name: "Home",
                    id: 1,
                    to: '/',
                    button: false
                },
                {
                    name: "About",
                    id: 2,
                    to: 'about',
                    button: false
                },
                {
                    name: "Type of House",
                    id: 3,
                    to: 'houses',
                    button: false
                },
                {
                    name: "Contact",
                    id: 4,
                    to: 'contact',
                    button: false
                }]
        }
    }
}
</script>
<template>
    <nav class="h-20 flex flex-row justify-between">
        <div class="mx-4">
            <h1>Hello</h1>
        </div>
        <div class="flex flex-row items-center justify-evenly mx-2 w-[60%]">

            <ul v-for="navitem in navitems" :key="navitem.id">
                <NuxtLink :class="'font-semibold'" :to=navitem.to>{{ navitem.name }}</NuxtLink>
            </ul>
            <button :class="'font-semibold w-[7rem] h-[2rem] border-2 rounded-md hover:bg-slate-200'">Login</button>

        </div>
    </nav>
    <div>
        <slot />
    </div>
</template>