<template>
    <div class="w-full relative px-2 lg:px-0 mt-6 lg:mt-0 pb-12">
        <div class="w-full sm:w-5/6 lg:w-5/6 xl:w-3/6 mx-auto shadow-xl bg-white h-88 -mt-0 lg:-mt-16 z-10 rounded py-6 px-2 sm:px-6">
            <div class="mb-8 w-full text-center lg:text-left">
                <h3 class="text-primary text-lg lg:text-xl font-medium tracking-wider">We use the real exchange rate</h3>
               <div class="w-full flex flex-col lg:flex-row justify-between items-center tracking-wide font-medium"> 
                    <p class="text-text-calculator text-sm leading-6">As of 1 min ago, 1 GBP → 527.952 NGN</p>
                    <p class="text-text-calculator text-sm leading-6 hidden lg:block">Mid market rate <span class="px-1 text-xs font-medium rounded-full border border-accent text-accent">?</span></p>
                </div>
            </div>
            <apexchart class="w-full font-sans"
               type="area" height="300"
                :options="options" :series="series">
            </apexchart>  
            <div class="w-full flex justify-center items-center py-2 mt-4">
                <button class="border border-accent text-accent rounded px-6 py-2 font-medium hover:text-white hover:bg-accent">Track This Exchange</button>
            </div>
        </div>
        <div class="w-full sm:w-5/6 lg:w-5/6 xl:w-3/6 mx-auto py-6 flex flex-col lg:flex-row mt-4 space-x-0 lg:space-x-4">
            <p class="text-lg lg:text-2xl font-bold text-primary tracking-wide w-full lg:w-2/6 text-center lg:text-left mb-2">No hidden fees<span class="text-accent">.</span> </p>
            <p class="w-full text-sm lg:text-base lg:w-4/6 px-4 lg:px-6 text-secondary ">
                We’re on a mission to bring transparency to finance. We charge as little as possible, and we always show you upfront. No hidden fees. No bad exchange rates. No surprises.
            </p>
        </div>
    </div>
</template>

<script>

export default {
    data(){
        return{
            options: {
      chart: {
        id: 'vuechart-example'
      },
      colors:['#1FC7A2', '#1FC7A2', '#2ED16E'],
      fill: {
        type: 'gradient',
        gradient: {
            shade: 'light',
            type: "horizontal",
            shadeIntensity: 0.1,
            gradientToColors: ["#eaf8fd", "ebf9f6", "#ecfaf0"], // optional, if not defined - uses the shades of same color in series
            inverseColors: true,
            opacityFrom: 0.1,
            opacityTo: 0.4,
            stops: [0, 20, 50],
            colorStops: []
        }
      },
      xaxis: {
        categories: [
         "Jan 1",
         "Jan 2",
         "Jan 3",
         "Jan 4",
         "Jan 5",
         "Jan 6",
         "Jan 7",
         "Jan 8",
        ]
      }
    },
    series: [{
      name: 'series-1',
      data: [55, 62, 89, 66, 98, 72, 101, 75]
    }]
        }
    }
}
</script>