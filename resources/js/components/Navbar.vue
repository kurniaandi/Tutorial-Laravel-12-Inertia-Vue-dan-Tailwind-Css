<template>
  <nav class="relative flex flex-wrap items-center justify-between px-0 py-2 mx-6 transition-all ease-in shadow-none duration-250 rounded-2xl lg:flex-nowrap lg:justify-start">
    <div class="flex items-center justify-between w-full px-4 py-1 mx-auto flex-wrap-inherit">
      <!-- Breadcrumb -->
      <nav>
        <ol class="flex flex-wrap pt-1 mr-12 bg-transparent rounded-lg sm:mr-16">
          <li class="text-sm leading-normal">
            <a href="/" class="text-white">Home /</a>
          </li>
          <li class="text-sm pl-2 capitalize leading-normal text-white before:float-left before:pr-2 before:text-white before:content-['/']">
            <a href="#" class="opacity-50 hover:underline">Dashboard</a>
          </li>
        </ol>
      </nav>

      <!-- Search and Actions -->
      <div class="flex items-center mt-2 grow sm:mt-0 sm:mr-6 md:mr-0 lg:flex lg:basis-auto">
        <!-- Search -->
        <div class="relative w-full max-w-xs md:ml-auto md:pr-4">
          <div class="relative flex items-center w-full rounded-lg border border-gray-300 bg-white dark:bg-slate-850 dark:border-slate-700">
            <span class="absolute left-2 flex items-center text-slate-500 dark:text-slate-400 pointer-events-none">
              <i class="fas fa-search"></i>
            </span>
            <input
              type="text"
              placeholder="Type here..."
              class="pl-9 pr-3 py-2 w-full text-sm leading-6 rounded-lg bg-transparent focus:outline-none focus:ring-1 focus:ring-blue-500 dark:text-white dark:placeholder:text-slate-500"
              disabled
            />
          </div>
        </div>

        <!-- Actions -->
        <ul class="flex flex-row justify-end pl-0 mb-0 list-none md-max:w-full">
          <!-- Logout -->
          <li class="flex items-center">
            <a href="#" class="block px-0 py-2 text-sm font-semibold text-white transition-all ease-nav-brand">
              <i class="fa fa-power-off sm:mr-1"></i>
              <span class="hidden sm:inline">Log Out</span>
            </a>
          </li>

          <!-- Hamburger -->
          <li class="flex items-center pl-4 xl:hidden">
            <button class="block p-0 text-white transition-all ease-nav-brand text-sm">
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
</script>
