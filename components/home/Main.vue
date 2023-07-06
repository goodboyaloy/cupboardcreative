<template>
    <div class="relative h-[90vh] flex flex-col bg-gradient">
        <div class="m-10 border-2 flex flex-col flex-grow border-white p-10 items-center justify-between">
            <NuxtImg src="/logo.png" class="w-20 object-contain" />
            <div class="flex flex-col items-center justify-center">
                <h1 class="max-w-2xl text-center leading-snug text-white text-5xl">
                    the <span class="font-semibold">intersection</span> where creativity meets <span
                        class="font-semibold">strategy</span>
                </h1>
                <div class="flex items-center mt-10">
                    <div v-for="route in routes" :class="{ 'group relative inline-block': route.routes }">
                        <NuxtLink
                            class="text-white px-5 opacity-80 hover:opacity-100 uppercase hover:font-semibold duration-500"
                            :to="route.path">{{ route.label }}
                        </NuxtLink>
                        <div v-if="route.routes"
                            class="flex flex-col py-6 absolute top-full left-1/2 z-20 mt-5 -translate-x-1/2 whitespace-nowrap rounded border bg-white text-sm opacity-0 group-hover:opacity-100">
                            <span
                                class="absolute -top-2.5 left-1/2 -z-10 h-5 w-5 -translate-x-1/2 rotate-45 rounded-sm border-t border-l bg-white"></span>
                            <NuxtLink
                                class="px-10 py-4 text-neutral-500 hover:text-secondary uppercase whitespace-nowrap duration-500"
                                :to="route.path" v-for="childRoute in route.routes"> {{ childRoute.label }}
                            </NuxtLink>
                        </div>
                    </div>
                </div>
            </div>
            <span />
        </div>
    </div>
</template>

<script setup lang="ts">
import routes from '~~/constants/routes';
</script>