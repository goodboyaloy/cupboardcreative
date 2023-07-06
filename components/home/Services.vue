<template>
    <div class="relative flex flex-col bg-gradient-alt">
        <div class="py-32 w-full max-w-7xl mx-auto flex flex-col gap-20">
            <div class="flex items-start"> 
                <h2 class="font-semibold text-3xl text-white lowercase w-1/3">embracing change: unlocking limitless
                    possibilities</h2>
                <p class="text-white w-2/3">We tailor strategies to meet evolving needs and challenges. Just as a simple box
                    surprises with its versatility, we craft ingenious and customised solutions that transcend boundaries.
                </p>
            </div>
            <div class="flex flex-col gap-10">
                <div class="px-10 py-20 bg-white rounded-[3rem] border" v-for="service in services">
                    <div class="max-w-md">
                        <p class="uppercase text-neutral-500">{{ service.description }}</p>
                        <h3 class="uppercase font-bold mt-5 mb-10 text-5xl text-gradient">{{ service.label }}</h3>

                        <NuxtLink :to="service.path" class="flex items-center gap-2.5 text-neutral-500 uppercase text-xl">
                            Learn more
                            <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 shrink-0" viewBox="0 0 24 24">
                                <path fill="currentColor"
                                    d="m14 18l-1.4-1.45L16.15 13H4v-2h12.15L12.6 7.45L14 6l6 6l-6 6Z" />
                            </svg>
                        </NuxtLink>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script setup lang="ts">
import services from '~~/constants/services';
</script>