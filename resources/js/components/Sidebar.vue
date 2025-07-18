<template>
  <aside :class="[
    'fixed inset-y-0 flex-wrap items-center justify-between block w-full p-0 my-4 overflow-y-auto antialiased transition-transform duration-200 bg-white border-0 shadow-xl dark:shadow-none dark:bg-slate-850 max-w-64 ease-nav-brand z-990 xl:ml-6 rounded-2xl xl:left-0 xl:translate-x-0',
    isOpen ? 'translate-x-0' : '-translate-x-full'
  ]" aria-expanded="false">
    <div class="h-19">
      <i @click="$emit('close')"
        class="absolute top-0 right-0 p-4 opacity-50 cursor-pointer fas fa-times dark:text-white text-slate-400 xl:hidden"></i>
      <Link class="block px-8 py-6 m-0 text-sm whitespace-nowrap dark:text-white text-slate-700" href="/"
        target="_blank">
      <img src="/assets/img/logo-ct-dark.png"
        class="inline h-full max-w-full transition-all duration-200 dark:hidden ease-nav-brand max-h-8"
        alt="main_logo" />
      <img src="/assets/img/logo-ct.png"
        class="hidden h-full max-w-full transition-all duration-200 dark:inline ease-nav-brand max-h-8"
        alt="main_logo" />
      <span class="ml-1 font-semibold transition-all duration-200 ease-nav-brand">Argon Dashboard 2</span>
      </Link>
    </div>

    <hr
      class="h-px mt-0 bg-transparent bg-gradient-to-r from-transparent via-black/40 to-transparent dark:bg-gradient-to-r dark:from-transparent dark:via-white dark:to-transparent" />

    <div class="items-center block w-auto max-h-screen overflow-auto h-sidenav grow basis-full">
      <ul class="flex flex-col pl-0 mb-0">
        <li class="mt-0.5 w-full">
          <Link :href="route('admin')" :class="[
            'py-2.7 my-0 mx-2 flex items-center whitespace-nowrap rounded-lg px-4 font-semibold transition-colors',
            isActive('admin')
              ? 'bg-blue-500/13 dark:text-white dark:opacity-80 text-slate-700 border-l-4 border-blue-300'
              : 'text-sm ease-nav-brand dark:text-white dark:opacity-80 text-slate-500 hover:bg-blue-100'
          ]">
          <div class="mr-2 flex h-8 w-8 items-center justify-center rounded-lg bg-center stroke-0 text-center xl:p-2.5">
            <i class="relative top-0 text-sm leading-normal text-blue-500 ni ni-tv-2"></i>
          </div>
          <span class="ml-1 duration-300 opacity-100 pointer-events-none ease">Dashboard</span>
          </Link>
        </li>
        <template v-if="hasRole('super_admin')">
          <li class="mt-0.5 w-full">
            <Link :href="route('users.index')" :class="[
              'py-2.5 my-0 mx-2 flex items-center whitespace-nowrap px-4 transition-colors rounded-lg',
              isActive('users.index')
                ? 'dark:text-white dark:opacity-80 font-semibold text-blue-600 bg-blue-100 border-l-4 border-blue-300'
                : 'text-sm ease-nav-brand dark:text-white dark:opacity-80 text-slate-500 hover:bg-blue-100'
            ]">
            <div class="mr-2 flex h-8 w-8 items-center justify-center rounded-lg bg-center text-center xl:p-2.5">
              <i class="text-sm leading-normal text-orange-500 ni ni-single-02"></i>
            </div>
            <span class="ml-1 duration-300 opacity-100 pointer-events-none ease">Users</span>
            </Link>
          </li>
        </template>
        <li class="mt-0.5 w-full">
          <Link :href="route('kunjungans.index')" :class="[
            'py-2.5 my-0 mx-2 flex items-center whitespace-nowrap px-4 transition-colors rounded-lg',
            isActive('kunjungans.index')
              ? 'dark:text-white dark:opacity-80 font-semibold text-blue-600 bg-blue-100 border-l-4 border-blue-300'
              : 'text-sm ease-nav-brand dark:text-white dark:opacity-80 text-slate-500 hover:bg-blue-100'
          ]">
          <div class="mr-2 flex h-8 w-8 items-center justify-center rounded-lg bg-center text-center xl:p-2.5">
            <i class="text-sm leading-normal text-green-500 ni ni-send"></i>
          </div>
          <span class="ml-1 duration-300 opacity-100 pointer-events-none ease">Kunjungan</span>
          </Link>
        </li>
        <li class="mt-0.5 w-full">
          <Link :href="route('order-obat.index')" :class="[
            'py-2.5 my-0 mx-2 flex items-center whitespace-nowrap px-4 transition-colors rounded-lg',
            isActive('order-obat.index')
              ? 'dark:text-white dark:opacity-80 font-semibold text-blue-600 bg-blue-100 border-l-4 border-blue-300'
              : 'text-sm ease-nav-brand dark:text-white dark:opacity-80 text-slate-500 hover:bg-blue-100'
          ]">
          <div class="mr-2 flex h-8 w-8 items-center justify-center rounded-lg bg-center text-center xl:p-2.5">
            <i class="text-sm leading-normal text-green-500 ni ni-ambulance"></i>
          </div>
          <span class="ml-1 duration-300 opacity-100 pointer-events-none ease">Apply Obat</span>
          </Link>
        </li>

        <li class="mt-0.5 w-full">
          <Link :href="route('order-obat-histories.index')" :class="[
            'py-2.5 my-0 mx-2 flex items-center whitespace-nowrap px-4 transition-colors rounded-lg',
            isActive('order-obat-histories.index')
              ? 'dark:text-white dark:opacity-80 font-semibold text-blue-600 bg-blue-100 border-l-4 border-blue-300'
              : 'text-sm ease-nav-brand dark:text-white dark:opacity-80 text-slate-500 hover:bg-blue-100'
          ]">
          <div class="mr-2 flex h-8 w-8 items-center justify-center rounded-lg bg-center text-center xl:p-2.5">
            <!-- Contoh ganti icon: dari ni-send ke ni-basket (ikon keranjang) -->
            <i class="text-sm leading-normal text-purple-500 ni ni-basket"></i>
          </div>
          <span class="ml-1 duration-300 opacity-100 pointer-events-none ease">Order Obat Histories</span>
          </Link>
        </li>
        <li class="mt-0.5 w-full">
          <Link :href="route('roles.index')" :class="[
            'py-2.5 my-0 mx-2 flex items-center whitespace-nowrap px-4 transition-colors rounded-lg',
            isActive('roles.index')
              ? 'dark:text-white dark:opacity-80 font-semibold text-blue-600 bg-blue-100 border-l-4 border-blue-300'
              : 'text-sm ease-nav-brand dark:text-white dark:opacity-80 text-slate-500 hover:bg-blue-100'
          ]">
          <div class="mr-2 flex h-8 w-8 items-center justify-center rounded-lg bg-center text-center xl:p-2.5">
            <i class="text-sm leading-normal text-blue-500 ni ni-lock-circle-open"></i>
          </div>
          <span class="ml-1 duration-300 opacity-100 pointer-events-none ease">Roles</span>
          </Link>
        </li>
        <li class="mt-0.5 w-full">
          <Link :href="route('dokters.index')" :class="[
            'py-2.5 my-0 mx-2 flex items-center whitespace-nowrap px-4 transition-colors rounded-lg',
            isActive('dokters.index')
              ? 'dark:text-white dark:opacity-80 font-semibold text-blue-600 bg-blue-100 border-l-4 border-blue-300'
              : 'text-sm ease-nav-brand dark:text-white dark:opacity-80 text-slate-500 hover:bg-blue-100'
          ]">
          <div class="mr-2 flex h-8 w-8 items-center justify-center rounded-lg bg-center text-center xl:p-2.5">
            <!-- Ganti icon ni-single-copy-04 menjadi icon untuk Dokter -->
            <i class="text-sm leading-normal text-cyan-500 ni ni-user-run"></i>
          </div>
          <span class="ml-1 duration-300 opacity-100 pointer-events-none ease">Dokter</span>
          </Link>
        </li>
        <li class="mt-0.5 w-full">
          <Link :href="route('obats.index')" :class="[
            'py-2.5 my-0 mx-2 flex items-center whitespace-nowrap px-4 transition-colors rounded-lg',
            isActive('obats.index')
              ? 'dark:text-white dark:opacity-80 font-semibold text-blue-600 bg-blue-100 border-l-4 border-blue-300'
              : 'text-sm ease-nav-brand dark:text-white dark:opacity-80 text-slate-500 hover:bg-blue-100'
          ]">
          <div class="mr-2 flex h-8 w-8 items-center justify-center rounded-lg bg-center text-center xl:p-2.5">
            <!-- Icon untuk Obat -->
            <i class="text-sm leading-normal text-purple-500 ni ni-caps-small"></i>
          </div>
          <span class="ml-1 duration-300 opacity-100 pointer-events-none ease">Obat</span>
          </Link>
        </li>
        <li class="mt-0.5 w-full">
          <Link :href="route('satuan-obats.index')" :class="[
            'py-2.5 my-0 mx-2 flex items-center whitespace-nowrap px-4 transition-colors rounded-lg',
            isActive('satuan-obats.index')
              ? 'dark:text-white dark:opacity-80 font-semibold text-blue-600 bg-blue-100 border-l-4 border-blue-300'
              : 'text-sm ease-nav-brand dark:text-white dark:opacity-80 text-slate-500 hover:bg-blue-100'
          ]">
          <div class="mr-2 flex h-8 w-8 items-center justify-center rounded-lg bg-center text-center xl:p-2.5">
            <!-- Icon untuk Satuan Obat -->
            <i class="text-sm leading-normal text-green-500 ni ni-box-2"></i>
          </div>
          <span class="ml-1 duration-300 opacity-100 pointer-events-none ease">Satuan Obat</span>
          </Link>
        </li>
        <li class="mt-0.5 w-full">
          <Link :href="route('konsumsi-obats.index')" :class="[
            'py-2.5 my-0 mx-2 flex items-center whitespace-nowrap px-4 transition-colors rounded-lg',
            isActive('konsumsi-obats.index')
              ? 'dark:text-white dark:opacity-80 font-semibold text-blue-600 bg-blue-100 border-l-4 border-blue-300'
              : 'text-sm ease-nav-brand dark:text-white dark:opacity-80 text-slate-500 hover:bg-blue-100'
          ]">
          <div class="mr-2 flex h-8 w-8 items-center justify-center rounded-lg bg-center text-center xl:p-2.5">
            <!-- Icon untuk Konsumsi Obat -->
            <i class="text-sm leading-normal text-green-500 ni ni-bullet-list-67"></i>
          </div>
          <span class="ml-1 duration-300 opacity-100 pointer-events-none ease">Konsumsi Obat</span>
          </Link>
        </li>

        <li class="mt-0.5 w-full">
          <Link :href="route('pasiens.index')" :class="[
            'py-2.5 my-0 mx-2 flex items-center whitespace-nowrap px-4 transition-colors rounded-lg',
            isActive('pasiens.index')
              ? 'dark:text-white dark:opacity-80 font-semibold text-blue-600 bg-blue-100 border-l-4 border-blue-300'
              : 'text-sm ease-nav-brand dark:text-white dark:opacity-80 text-slate-500 hover:bg-blue-100'
          ]">
          <div class="mr-2 flex h-8 w-8 items-center justify-center rounded-lg bg-center text-center xl:p-2.5">
            <i class="text-sm leading-normal text-orange-500 ni ni-single-02"></i>
          </div>
          <span class="ml-1 duration-300 opacity-100 pointer-events-none ease">Pasien</span>
          </Link>
        </li>

        <li class="mt-0.5 w-full">
          <Link :href="route('polikliniks.index')" :class="[
            'py-2.5 my-0 mx-2 flex items-center whitespace-nowrap px-4 transition-colors rounded-lg',
            isActive('polikliniks.index')
              ? 'dark:text-white dark:opacity-80 font-semibold text-blue-600 bg-blue-100 border-l-4 border-blue-300'
              : 'text-sm ease-nav-brand dark:text-white dark:opacity-80 text-slate-500 hover:bg-blue-100'
          ]">
          <div class="mr-2 flex h-8 w-8 items-center justify-center rounded-lg bg-center text-center xl:p-2.5">
            <i class="text-sm leading-normal text-emerald-500 ni ni-single-copy-04"></i>
          </div>
          <span class="ml-1 duration-300 opacity-100 pointer-events-none ease">Poliklinik</span>
          </Link>
        </li>

      </ul>
    </div>

    <!-- bagian bawah tetap sama -->
    <div class="mx-4">
      <!-- ... konten lainnya ... -->
    </div>
  </aside>
</template>

<script setup>
import { Link, usePage } from '@inertiajs/vue3'
import { usePermission } from '@/Composable/Permission'

const { hasRole } = usePermission();

const props = defineProps({
  isOpen: {
    type: Boolean,
    default: false,
  },
})
const emit = defineEmits(['close'])

const page = usePage()

function isActive(routeName) {
  const currentPath = new URL(page.url, window.location.origin).pathname
  const targetPath = new URL(route(routeName), window.location.origin).pathname

  return currentPath === targetPath || currentPath.startsWith(targetPath + '/')
}


</script>
