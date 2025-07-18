<template>
    <nav class="relative flex flex-wrap items-center justify-between px-0 py-2 mx-6 transition-all ease-in shadow-none duration-250 rounded-2xl lg:flex-nowrap lg:justify-start"
        navbar-main navbar-scroll="false">
        <div class="flex items-center justify-between w-full px-4 py-1 mx-auto flex-wrap-inherit">
            <nav>
                <ol class="flex flex-wrap pt-1 mr-12 bg-transparent rounded-lg sm:mr-16">
                    <li class="text-sm leading-normal">
                        <Link href="/" class="text-white">Home /</Link>
                    </li>
                    <li v-for="(crumb, index) in breadcrumbs" :key="index"
                        class="text-sm pl-2 capitalize leading-normal text-white"
                        :class="index !== 0 ? 'before:float-left before:pr-2 before:text-white before:content-[\'/\']' : ''">
                        <span v-if="crumb.href">
                            <Link :href="crumb.href" class="opacity-50 hover:underline">{{ crumb.label }}</Link>
                        </span>
                        <span v-else>{{ crumb.label }}</span>
                    </li>
                </ol>
            </nav>

            <div class="flex items-center mt-2 grow sm:mt-0 sm:mr-6 md:mr-0 lg:flex lg:basis-auto">
                <div class="relative w-full max-w-xs md:ml-auto md:pr-4">
                    <div
                        class="relative flex items-center w-full rounded-lg border border-gray-300 bg-white dark:bg-slate-850 dark:border-slate-700">
                        <span
                            class="absolute left-2 flex items-center text-slate-500 dark:text-slate-400 pointer-events-none">
                            <i class="fas fa-search"></i>
                        </span>
                        <input v-model="searchQuery" type="text" placeholder="Type here..."
                            class="pl-9 pr-3 py-2 w-full text-sm leading-6 rounded-lg bg-transparent focus:outline-none focus:ring-1 focus:ring-blue-500 dark:text-white dark:placeholder:text-slate-500" />
                    </div>

                    <!-- Dropdown hasil filter -->
                    <ul v-if="searchQuery.length > 0 && filteredMenu.length > 0"
                        class="absolute z-50 mt-1 max-h-48 w-full overflow-auto rounded-md bg-white py-1 shadow-lg ring-1 ring-black ring-opacity-5 focus:outline-none dark:bg-slate-800">
                        <li v-for="item in filteredMenu" :key="item.name"
                            class="cursor-pointer select-none py-2 px-4 text-gray-900 dark:text-white hover:bg-blue-500 hover:text-white"
                            @click="navigateTo(item.route)">
                            {{ item.name }}
                        </li>
                    </ul>
                    <div v-else-if="searchQuery.length > 0 && filteredMenu.length === 0"
                        class="absolute z-50 mt-1 w-full rounded-md bg-white py-2 px-4 text-gray-500 dark:bg-slate-800">
                        No results found
                    </div>
                </div>

                <ul class="flex flex-row justify-end pl-0 mb-0 list-none md-max:w-full">
                    <li class="flex items-center">
                        <button @click="logout"
                            class="block px-0 py-2 text-sm font-semibold text-white transition-all ease-nav-brand">
                            <i class="fa fa-power-off sm:mr-1"></i>
                            <span class="hidden sm:inline">Log Out</span>
                        </button>
                    </li>

                    <!-- Hamburger Button -->
                    <li class="flex items-center pl-4 xl:hidden">
                        <button @click="$emit('toggleSidebar')"
                            class="block p-0 text-white transition-all ease-nav-brand text-sm">
                            <div class="w-4.5 overflow-hidden">
                                <i class="ease mb-0.75 relative block h-0.5 rounded-sm bg-white transition-all"></i>
                                <i class="ease mb-0.75 relative block h-0.5 rounded-sm bg-white transition-all"></i>
                                <i class="ease relative block h-0.5 rounded-sm bg-white transition-all"></i>
                            </div>
                        </button>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script setup>
import { ref, computed } from 'vue'
import { router, Link, usePage } from '@inertiajs/vue3'
import { route } from 'ziggy-js'

const emit = defineEmits(['toggleSidebar'])
const page = usePage()

// Menu utama
const menu = ref([
    { name: 'Dashboard', route: 'admin' },
    { name: 'Users', route: 'users.index' },
    { name: 'Roles', route: 'roles.index' },
    { name: 'Poliklinik', route: 'polikliniks.index' },
    { name: 'Logout', route: 'logout' },
])

// Search
const searchQuery = ref('')

// Filter menu berdasarkan search
const filteredMenu = computed(() => {
    if (!searchQuery.value) return []
    const q = searchQuery.value.toLowerCase()
    return menu.value.filter(item => item.name.toLowerCase().includes(q))
})

// Fungsi cek keberadaan route di Ziggy
function hasRoute(name) {
    try {
        route(name)
        return true
    } catch {
        return false
    }
}

// Navigasi
function navigateTo(routeName) {
    if (routeName === 'logout') {
        logout()
    } else {
        const url = route(routeName)
        router.get(url)
        searchQuery.value = ''
    }
}

// Logout
function logout() {
    router.post(route('logout'))
}

// Breadcrumb dinamis dengan pengecekan route
const breadcrumbs = computed(() => {
    const currentRouteName = page.props.currentRouteName || ''


    if (!currentRouteName) return []

    const parts = currentRouteName.split('.')

    const labels = {
        admin: 'Dashboard',
        users: 'Users',
        index: 'List',
        create: 'Create',
        edit: 'Edit',
        settings: 'Settings',
        billing: 'Billing',
        show: 'Detail'
    }

    const crumbs = []
    for (let i = 0; i < parts.length; i++) {
        const key = parts.slice(0, i + 1).join('.')
        const label = labels[parts[i]] ?? parts[i]

        // Hanya buat href jika route ada dan bukan crumb terakhir
        const href = (i < parts.length - 1 && hasRoute(key)) ? route(key) : null

        crumbs.push({ label, href })
    }

    return crumbs
})
</script>

