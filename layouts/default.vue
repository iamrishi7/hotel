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
                }
            ],
            'footer': [
                {
                    name: 'Links',
                    id: 1,
                    chlidren: [
                        {
                            name: "ItemA",
                            to: "/",
                        },
                        {
                            name: "ItemB",
                            to: "/",
                        },
                        {
                            name: "ItemC",
                            to: "/",
                        }
                    ]
                },
                {
                    name: 'Support',
                    id: 2,
                    chlidren: [
                        {
                            name: "ItemD",
                            to: "/",
                        },
                        {
                            name: "ItemE",
                            to: "/",
                        },
                        {
                            name: "ItemF",
                            to: "/",
                        }
                    ]
                },
                {
                    name: 'Contact Us',
                    id: 3,
                    chlidren: [
                        {
                            name: "ItemG",
                            to: "/",
                        },
                        {
                            name: "ItemH",
                            to: "/",
                        },
                        {
                            name: "ItemI",
                            to: "/",
                        }
                    ]
                }
            ]
        }
    }
}
</script>
<template>
    <nav class="flex flex-row justify-between">
        <div class="mx-4">
            <img :class="'w-40 h-22 '" src="~/assets/images/logo.png" alt="">
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
    <footer :class="'flex flex-col items-center justify-between'">
        <div :class="'text-center space-y-4'">
            <h1 class="text-5xl font-semibold">Get Better Deals</h1>
            <p class="text-slate-500">See why hundreds of tourists choose our resorts. Because we are the best and bla bla.
            </p>
            <div class="space-x-4 pt-4">
                <input class="border-2 w-64 rounded-md text-center h-10" type="text" placeholder="Drop your phone number">
                <button :class="'bg-[#1218c4] text-white rounded-md h-10 w-28 drop-shadow-xl'">Submit</button>
            </div>
        </div>
        <div class="divide-y">
            <div class="flex flex-row items-center justify-between h-[22rem] w-full">
                <div class="flex flex-col space-y-4">
                    <div :class="'ml-4 w-40 h-22'">
                        <img src="~/assets/images/logo.png" alt="">
                        <p :class="'ml-4 mt-4 text-center w-28 text-sm'">Connect with us</p>
                    </div>
                    <div class="flex flex-row items-center justify-around space-x-2">
                        <NuxtLink to="maps.google.com">
                            <Icon name="logos:google-maps" size="24px" />
                        </NuxtLink>
                        <NuxtLink to="instagram.com">
                            <Icon name="skill-icons:instagram" size="24px" />
                        </NuxtLink>
                        <NuxtLink to="facebook.com">
                            <Icon name="logos:facebook" size="24px" />
                        </NuxtLink>
                    </div>
                </div>
                <div class="flex flex-row justify-around w-[60rem]">
                    <ul v-for="foot in footer" :key="foot.id">
                        <li :class="'font-semibold'">
                            {{ foot.name }}
                            <ul class="mt-6 space-y-0.5 flex flex-col">
                                <NuxtLink :to="child.to" :class="'font-light text-slate-600'"
                                    v-for="child in foot.chlidren">
                                    {{ child.name }}
                                </NuxtLink>
                            </ul>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="flex flex-row space-x-6 justify-items-end text-slate-700">
                <NuxtLink to="privacy">Privacy and Policy</NuxtLink>
                <NuxtLink to="tnc">Terms & Conditions</NuxtLink>
            </div>
        </div>
    </footer>
</template>