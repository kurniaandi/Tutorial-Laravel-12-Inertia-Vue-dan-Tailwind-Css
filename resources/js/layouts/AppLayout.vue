<template>

    <body
        class="m-0 font-sans antialiased font-normal dark:bg-slate-900 text-base leading-default bg-gray-50 text-slate-500">
        <noscript>
            <iframe src="https://www.googletagmanager.com/ns.html?id=GTM-NKDMSK6" height="0" width="0"
                style="display:none;visibility:hidden">
            </iframe>
        </noscript>
        <div class="absolute w-full bg-blue-500 dark:hidden min-h-75"></div>

        <Sidebar :isOpen="isSidebarOpen" @close="isSidebarOpen = false" />

        <main class="relative h-full max-h-screen transition-all duration-200 ease-in-out xl:ml-68 rounded-xl">
  
            <Navbar :isSidebarOpen="isSidebarOpen" @toggleSidebar="isSidebarOpen = true" />

            <div class="w-full px-6 py-6 mx-auto">
                <slot />
                <Footer />
            </div>


        </main>
    </body>
</template>

<script>
import Sidebar from '@/components/Sidebar.vue'
import Navbar from '@/components/Navbar.vue'
import Footer from '@/components/Footer.vue'

export default {
    components: { Sidebar, Navbar, Footer },
    data() {
        return {
            isSidebarOpen: false
        }
    }
}
</script>
