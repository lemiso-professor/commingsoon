
<template>
                                                         <section class="py-24 relative">
        <div class="w-full max-w-7xl px-4 md:px-5 lg:px-5 mx-auto">
            <div class="w-full md:px-16 px-10 md:pt-16 pt-10 pb-10 bg-yellow-300 rounded-2xl flex-col justify-end items-center lg:gap-28 md:gap-16 gap-10 inline-flex">
                <div class="flex-col justify-end items-center lg:gap-16 gap-10 flex">
                    <img src="https://pagedone.io/asset/uploads/1717500460.png" alt="pagedone logo image" class="object-cover">
                    <div class="flex-col justify-center items-center gap-10 flex">
                        <div class="flex-col justify-start items-center gap-2.5 flex">
                            <h2 class="text-center text-blue-400 md:text-6xl text-5xl font-bold font-manrope leading-normal">Coming Soon</h2>
                            <p class="text-center text-blue-500 text-base font-normal leading-relaxed">Just 20 days remaining until the big reveal of our new product!</p>
                        </div>
                        <div class="flex items-start justify-center w-full gap-2 count-down-main">
                            <div class="timer flex flex-col gap-0.5">
                                <div class="">
                                    <h3 class="countdown-element days text-center text-white text-2xl font-bold font-manrope leading-9"></h3>
                                </div>
                                <p class="text-center text-gray-500 text-xs font-normal leading-normal w-full">DAYS</p>
                            </div>
                            <h3 class="w-3 text-center text-gray-500 text-2xl font-medium font-manrope leading-9">:</h3>
                            <div class="timer flex flex-col gap-0.5">
                                <div class="">
                                    <h3 class="countdown-element hours text-center text-white text-2xl font-bold font-manrope leading-9"></h3>
                                </div>
                                <p class="text-center text-gray-500 text-xs font-normal leading-normal w-full">HRS</p>
                            </div>
                            <h3 class="w-3 text-center text-gray-500 text-2xl font-medium font-manrope leading-9">:</h3>
                            <div class="timer flex flex-col gap-0.5">
                                <div class="">
                                    <h3 class="countdown-element minutes text-center text-white text-2xl font-bold font-manrope leading-9"></h3>
                                </div>
                                <p class="text-center text-gray-500 text-xs font-normal leading-normal w-full">MINS</p>
                            </div>
                            <h3 class="w-3 text-center text-gray-500 text-2xl font-medium font-manrope leading-9">:</h3>
                            <div class="timer flex flex-col gap-0.5">
                                <div class="">
                                    <h3 class="countdown-element seconds text-center text-white text-2xl font-bold font-manrope leading-9"></h3>
                                </div>
                                <p class="text-center text-gray-500 text-xs font-normal leading-normal w-full">SECS</p>
                            </div>
                        </div>
                        <div class="w-full flex-col justify-center items-center gap-5 flex">
                            <h6 class="text-center text-emerald-400 text-base font-semibold leading-relaxed">Launched Date: July 23, 2024</h6>
                            <div class="justify-center items-center gap-2.5 flex sm:flex-row flex-col">
                                
                            </div>
                        </div>
                    </div>
                </div>
                <p class="text-center text-gray-500 text-sm font-normal leading-snug">Get in touch with us: <a href="" class="hover:text-gray-100 transition-all duration-700 ease-in-out"> mail@pagedone.com</a></p>
            </div>
        </div>
    </section>
<!--Javascript-->

                                            
</template>

<script setup>

    // count-down timer
    let dest = new Date("mar 31, 2024 23:59:59").getTime();
    let x = setInterval(function () {
      let now = new Date().getTime();
      let diff = dest - now;
      // Check if the countdown has reached zero or negative
      if (diff <= 0) {
        // Set the destination date to the same day next month
        let nextMonthDate = new Date();
        nextMonthDate.setMonth(nextMonthDate.getMonth() + 1);

        // If the current month is December, set the destination date to the same day next year
        if (nextMonthDate.getMonth() === 0) {
          nextMonthDate.setFullYear(nextMonthDate.getFullYear() + 1);
        }

        dest = nextMonthDate.getTime();
        return; // Exit the function
      }

      let days = Math.floor(diff / (1000 * 60 * 60 * 24));
      let hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      let minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
      let seconds = Math.floor((diff % (1000 * 60)) / 1000);

      if (days < 10) {
        days = `0${days}`;
      }

      if (hours < 10) {
        hours = `0${hours}`;
      }
      if (minutes < 10) {
        minutes = `0${minutes}`;
      }
      if (seconds < 10) {
        seconds = `0${seconds}`;
      }

      // Get elements by class name
      let countdownElements = document.getElementsByClassName("countdown-element");

      // Loop through the elements and update their content
      for (let i = 0; i < countdownElements.length; i++) {
        let className = countdownElements[i].classList[1]; // Get the second class name
        switch (className) {
          case "days":
            countdownElements[i].innerHTML = days;
            break;
          case "hours":
            countdownElements[i].innerHTML = hours;
            break;
          case "minutes":
            countdownElements[i].innerHTML = minutes;
            break;
          case "seconds":
            countdownElements[i].innerHTML = seconds;
            break;
          default:
            break;
        }
      }
    }, 10);
  
</script>

<style lang="scss" scoped>

</style>