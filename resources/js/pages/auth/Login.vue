<template>
    <AuthLayout>
        <div
            class="flex flex-col w-full max-w-full px-3 mx-auto lg:mx-0 shrink-0 md:flex-0 md:w-7/12 lg:w-5/12 xl:w-4/12">
            <div
                class="relative flex flex-col min-w-0 break-words bg-transparent border-0 shadow-none lg:py4 rounded-2xl bg-clip-border">
                <div class="p-6 pb-0 mb-0">
                    <h4 class="font-bold">Sign In</h4>
                    <p class="mb-0">Enter your email and password to sign in</p>
                </div>

                <div class="flex-auto p-6">
                    <form @submit.prevent="submit">
                        <div v-if="form.errors.email || form.errors.password" class="mb-4 text-sm text-red-600">
                            {{ form.errors.email || form.errors.password }}
                        </div>

                        <div class="mb-4">
                            <input v-model="form.email" type="email" placeholder="Email"
                                class="focus:shadow-primary-outline dark:bg-gray-950 dark:placeholder:text-white/80 dark:text-white/80 text-sm leading-5.6 ease block w-full appearance-none rounded-lg border border-solid border-gray-300 bg-white bg-clip-padding p-3 font-normal text-gray-700 outline-none transition-all placeholder:text-gray-500 focus:border-fuchsia-300 focus:outline-none"
                                required autocomplete="username" />
                        </div>

                        <div class="mb-4">
                            <input v-model="form.password" type="password" placeholder="Password"
                                class="focus:shadow-primary-outline dark:bg-gray-950 dark:placeholder:text-white/80 dark:text-white/80 text-sm leading-5.6 ease block w-full appearance-none rounded-lg border border-solid border-gray-300 bg-white bg-clip-padding p-3 font-normal text-gray-700 outline-none transition-all placeholder:text-gray-500 focus:border-fuchsia-300 focus:outline-none"
                                required autocomplete="current-password" />
                        </div>

                        <div class="flex items-center pl-12 mb-0.5 text-left min-h-6">
                            <input id="rememberMe" v-model="form.remember"
                                class="mt-0.5 rounded-10 duration-250 ease-in-out after:rounded-circle after:shadow-2xl after:duration-250 checked:after:translate-x-5.3 h-5 relative float-left -ml-12 w-10 cursor-pointer appearance-none border border-solid border-gray-200 bg-zinc-700/10 bg-none bg-contain bg-left bg-no-repeat align-top transition-all after:absolute after:top-px after:h-4 after:w-4 after:translate-x-px after:bg-white after:content-[''] checked:border-blue-500/95 checked:bg-blue-500/95 checked:bg-none checked:bg-right"
                                type="checkbox" />
                            <label class="ml-2 font-normal cursor-pointer select-none text-sm text-slate-700"
                                for="rememberMe">Remember me</label>
                        </div>

                        <div class="text-center">
                            <button type="submit" :disabled="form.processing"
                                :class="{ 'opacity-50 cursor-not-allowed': form.processing }"
                                class="inline-block w-full px-16 py-3.5 mt-6 mb-0 font-bold leading-normal text-center text-white align-middle transition-all bg-blue-500 border-0 rounded-lg cursor-pointer hover:-translate-y-px active:opacity-85 hover:shadow-xs text-sm ease-in tracking-tight-rem shadow-md bg-150 bg-x-25">
                                Sign in
                            </button>
                        </div>
                    </form>
                </div>

                <div class="text-center pt-0 px-1 sm:px-6">
                    <p class="text-sm">
                        Don't have an account?
                        <Link href="/register" class="text-blue-500 font-semibold">Sign up</Link>
                    </p>
                </div>
            </div>
        </div>
    </AuthLayout>
</template>

<script setup>
import { useForm, Link } from '@inertiajs/vue3'
import AuthLayout from '@/layouts/AuthenticatedLayout.vue'

const form = useForm({
    email: '',
    password: '',
    remember: false,
})

function submit() {
    form.post(route('login'), {
        onFinish: () => form.reset('password'),
    })
}
</script>
