<template>
    <AppLayout>
        <template #default>
             <Head title="Dashboard" />
            <div class="flex flex-wrap -mx-3">
                <!-- card1 -->
                <div class="w-full max-w-full px-3 mb-6 sm:w-1/2 sm:flex-none xl:mb-0 xl:w-1/4">
                    <div
                        class="relative flex flex-col min-w-0 break-words bg-white shadow-xl dark:bg-slate-850 dark:shadow-dark-xl rounded-2xl bg-clip-border">
                        <div class="flex-auto p-4">
                            <div class="flex flex-row -mx-3">
                                <div class="flex-none w-2/3 max-w-full px-3">
                                    <div>
                                        <p
                                            class="mb-0 font-sans text-sm font-semibold leading-normal uppercase dark:text-white dark:opacity-60">
                                            Today's Money</p>
                                        <h5 class="mb-2 font-bold dark:text-white">$53,000</h5>
                                        <p class="mb-0 dark:text-white dark:opacity-60">
                                            <span class="text-sm font-bold leading-normal text-emerald-500">+55%</span>
                                            since yesterday
                                        </p>
                                    </div>
                                </div>
                                <div class="px-3 text-right basis-1/3">
                                    <div
                                        class="inline-block w-12 h-12 text-center rounded-circle bg-gradient-to-tl from-blue-500 to-violet-500">
                                        <i
                                            class="ni leading-none ni-money-coins text-lg relative top-3.5 text-white"></i>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- card2 -->
                <div class="w-full max-w-full px-3 mb-6 sm:w-1/2 sm:flex-none xl:mb-0 xl:w-1/4">
                    <div
                        class="relative flex flex-col min-w-0 break-words bg-white shadow-xl dark:bg-slate-850 dark:shadow-dark-xl rounded-2xl bg-clip-border">
                        <div class="flex-auto p-4">
                            <div class="flex flex-row -mx-3">
                                <div class="flex-none w-2/3 max-w-full px-3">
                                    <div>
                                        <p
                                            class="mb-0 font-sans text-sm font-semibold leading-normal uppercase dark:text-white dark:opacity-60">
                                            Today's Users</p>
                                        <h5 class="mb-2 font-bold dark:text-white">2,300</h5>
                                        <p class="mb-0 dark:text-white dark:opacity-60">
                                            <span class="text-sm font-bold leading-normal text-emerald-500">+3%</span>
                                            since last week
                                        </p>
                                    </div>
                                </div>
                                <div class="px-3 text-right basis-1/3">
                                    <div
                                        class="inline-block w-12 h-12 text-center rounded-circle bg-gradient-to-tl from-red-600 to-orange-600">
                                        <i class="ni leading-none ni-world text-lg relative top-3.5 text-white"></i>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- card3 -->
                <div class="w-full max-w-full px-3 mb-6 sm:w-1/2 sm:flex-none xl:mb-0 xl:w-1/4">
                    <div
                        class="relative flex flex-col min-w-0 break-words bg-white shadow-xl dark:bg-slate-850 dark:shadow-dark-xl rounded-2xl bg-clip-border">
                        <div class="flex-auto p-4">
                            <div class="flex flex-row -mx-3">
                                <div class="flex-none w-2/3 max-w-full px-3">
                                    <div>
                                        <p
                                            class="mb-0 font-sans text-sm font-semibold leading-normal uppercase dark:text-white dark:opacity-60">
                                            New Clients</p>
                                        <h5 class="mb-2 font-bold dark:text-white">+3,462</h5>
                                        <p class="mb-0 dark:text-white dark:opacity-60">
                                            <span class="text-sm font-bold leading-normal text-red-600">-2%</span>
                                            since last quarter
                                        </p>
                                    </div>
                                </div>
                                <div class="px-3 text-right basis-1/3">
                                    <div
                                        class="inline-block w-12 h-12 text-center rounded-circle bg-gradient-to-tl from-emerald-500 to-teal-400">
                                        <i
                                            class="ni leading-none ni-paper-diploma text-lg relative top-3.5 text-white"></i>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- card4 -->
                <div class="w-full max-w-full px-3 sm:w-1/2 sm:flex-none xl:w-1/4">
                    <div
                        class="relative flex flex-col min-w-0 break-words bg-white shadow-xl dark:bg-slate-850 dark:shadow-dark-xl rounded-2xl bg-clip-border">
                        <div class="flex-auto p-4">
                            <div class="flex flex-row -mx-3">
                                <div class="flex-none w-2/3 max-w-full px-3">
                                    <div>
                                        <p
                                            class="mb-0 font-sans text-sm font-semibold leading-normal uppercase dark:text-white dark:opacity-60">
                                            Sales</p>
                                        <h5 class="mb-2 font-bold dark:text-white">$103,430</h5>
                                        <p class="mb-0 dark:text-white dark:opacity-60">
                                            <span class="text-sm font-bold leading-normal text-emerald-500">+5%</span>
                                            than last month
                                        </p>
                                    </div>
                                </div>
                                <div class="px-3 text-right basis-1/3">
                                    <div
                                        class="inline-block w-12 h-12 text-center rounded-circle bg-gradient-to-tl from-orange-500 to-yellow-500">
                                        <i class="ni leading-none ni-cart text-lg relative top-3.5 text-white"></i>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- cards row 2 -->
            <div class="flex flex-wrap mt-6 -mx-3">
                <div class="w-full max-w-full px-3 mt-0 lg:w-7/12 lg:flex-none">
                    <div class="border-black/12.5 dark:bg-slate-850 dark:shadow-dark-xl shadow-xl relative z-20 flex min-w-0 flex-col break-words rounded-2xl border-0 border-solid bg-white bg-clip-border"
                        style="height: 400px;">
                        <div class="border-black/12.5 mb-0 rounded-t-2xl border-b-0 border-solid p-6 pt-4 pb-0">
                            <h6 class="capitalize dark:text-white">Sales overview</h6>
                            <p class="mb-0 text-sm leading-normal dark:text-white dark:opacity-60">
                                <i class="fa fa-arrow-up text-emerald-500"></i>
                                <span class="font-semibold">4% more</span> in 2021
                            </p>
                        </div>
                        <div class="flex-auto p-4" style="position: relative; height: 300px;">
                            <canvas ref="chartCanvas"></canvas>
                        </div>
                    </div>
                </div>
                <div class="w-full max-w-full px-3 lg:w-5/12 lg:flex-none">
                    <div slider class="relative w-full h-full overflow-hidden rounded-2xl">
                        <!-- slide 1 -->
                        <div slide class="absolute w-full h-full transition-all duration-500">
                            <img class="object-cover h-full" src="/assets/img/carousel-1.jpg" alt="carousel image" />
                            <div
                                class="block text-start ml-12 left-0 bottom-0 absolute right-[15%] pt-5 pb-5 text-white">
                                <div
                                    class="inline-block w-8 h-8 mb-4 text-center text-black bg-white bg-center rounded-lg fill-current stroke-none">
                                    <i class="top-0.75 text-xxs relative text-slate-700 ni ni-camera-compact"></i>
                                </div>
                                <h5 class="mb-1 text-white">Get started with Argon</h5>
                                <p class="dark:opacity-80">There’s nothing I really wanted to do in life that I wasn’t
                                    able to get good at.</p>
                            </div>
                        </div>

                        <!-- slide 2 -->
                        <div slide class="absolute w-full h-full transition-all duration-500">
                            <img class="object-cover h-full" src="/assets/img/carousel-2.jpg" alt="carousel image" />
                            <div
                                class="block text-start ml-12 left-0 bottom-0 absolute right-[15%] pt-5 pb-5 text-white">
                                <div
                                    class="inline-block w-8 h-8 mb-4 text-center text-black bg-white bg-center rounded-lg fill-current stroke-none">
                                    <i class="top-0.75 text-xxs relative text-slate-700 ni ni-bulb-61"></i>
                                </div>
                                <h5 class="mb-1 text-white">Faster way to create web pages</h5>
                                <p class="dark:opacity-80">That’s my skill. I’m not really specifically talented at
                                    anything except for the ability to learn.</p>
                            </div>
                        </div>

                        <!-- slide 3 -->
                        <div slide class="absolute w-full h-full transition-all duration-500">
                            <img class="object-cover h-full" src="/assets/img/carousel-3.jpg" alt="carousel image" />
                            <div
                                class="block text-start ml-12 left-0 bottom-0 absolute right-[15%] pt-5 pb-5 text-white">
                                <div
                                    class="inline-block w-8 h-8 mb-4 text-center text-black bg-white bg-center rounded-lg fill-current stroke-none">
                                    <i class="top-0.75 text-xxs relative text-slate-700 ni ni-trophy"></i>
                                </div>
                                <h5 class="mb-1 text-white">Share with us your design tips!</h5>
                                <p class="dark:opacity-80">Don’t be afraid to be wrong because you can’t learn anything
                                    from a compliment.</p>
                            </div>
                        </div>

                        <!-- Control buttons -->
                        <button btn-next
                            class="absolute z-10 w-10 h-10 p-2 text-lg text-white border-none opacity-50 cursor-pointer hover:opacity-100 far fa-chevron-right active:scale-110 top-6 right-4"></button>
                        <button btn-prev
                            class="absolute z-10 w-10 h-10 p-2 text-lg text-white border-none opacity-50 cursor-pointer hover:opacity-100 far fa-chevron-left active:scale-110 top-6 right-16"></button>
                    </div>
                </div>
            </div>
        </template>
    </AppLayout>
</template>

<script setup>
import AppLayout from '@/layouts/AppLayout.vue'
import { Head } from '@inertiajs/vue3'
import { onMounted, ref } from 'vue'

const props = defineProps({
  labels: Array,
  data: Array
})

const chartCanvas = ref(null)

onMounted(() => {
  if (!window.Chart) {
    console.error('Chart.js belum ter-load! Pastikan script Chart.js sudah include.')
    return
  }

  const ctx = chartCanvas.value.getContext('2d')

  const gradientStroke1 = ctx.createLinearGradient(0, 230, 0, 50)
  gradientStroke1.addColorStop(1, 'rgba(94, 114, 228, 0.2)')
  gradientStroke1.addColorStop(0.2, 'rgba(94, 114, 228, 0.0)')
  gradientStroke1.addColorStop(0, 'rgba(94, 114, 228, 0)')

  new window.Chart(ctx, {
    type: 'line',
    data: {
      labels: props.labels,
      datasets: [
        {
          label: 'Mobile apps',
          tension: 0.4,
          pointRadius: 0,
          borderColor: '#5e72e4',
          backgroundColor: gradientStroke1,
          borderWidth: 3,
          fill: true,
          data: props.data,
          maxBarThickness: 6,
        },
      ],
    },
    options: {
      responsive: true,
      maintainAspectRatio: false,
      plugins: {
        legend: {
          display: false,
        },
      },
      interaction: {
        intersect: false,
        mode: 'index',
      },
      scales: {
        y: {
          grid: {
            drawBorder: false,
            display: true,
            drawOnChartArea: true,
            drawTicks: false,
            borderDash: [5, 5],
          },
          ticks: {
            display: true,
            padding: 10,
            color: '#fbfbfb',
            font: {
              size: 11,
              family: 'Open Sans',
              style: 'normal',
              lineHeight: 2,
            },
          },
        },
        x: {
          grid: {
            drawBorder: false,
            display: false,
            drawOnChartArea: false,
            drawTicks: false,
            borderDash: [5, 5],
          },
          ticks: {
            display: true,
            color: '#ccc',
            padding: 20,
            font: {
              size: 11,
              family: 'Open Sans',
              style: 'normal',
              lineHeight: 2,
            },
          },
        },
      },
    },
  })
})
</script>

