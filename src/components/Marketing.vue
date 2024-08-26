<script setup>
import { onMounted, ref } from "vue";

    // onMounted( ()=> {
    //     let counters = document.querySelectorAll(".counts")
    //     let interval = 5000;
    //     counters.forEach( function(item) {
    //         let startValue = 0;
    //         let endValue = parseInt(item.getAttribute("data-val"));
    //         console.log(endValue);
    //         let duration =Math.floor(interval / endValue )
    //         let counter = setInterval(function () {
    //             startValue += 1;
    //             item.textContent = startValue;
    //             if (startValue == endValue) {
    //                 clearInterval(counter);
    //             }
    //         }, duration)
    //     } )
    // } )

    // onMounted( ()=> { 
    //     let container = document.querySelector(".counters")
    //     let counters = document.querySelectorAll(".counts")
    //     let activated = false
    //     console.log(container)
    //     console.log(counters)
    //     window.addEventListener("scroll", ()=> {
    //         if ( pageYOffset > container.offsetTop - container.offsetHeight - 200 && activated === false )
    //             {
    //                 counters.forEach( function(counter) {
    //                     let count = 0;
    //                     function incrementCount() {
    //                         const target = parseInt(counter.getAttribute("data-val"));
    //                         if( count < target ) {
    //                             count++
    //                             counter.innerText = count;
    //                             setTimeout(incrementCount, 50);

    //                         } else {
    //                             counter.innerText = target;
    //                         }
    //                     }
    //                     incrementCount();
    //                     activated = true

    //                 } )
    //             } else if (pageYOffset < container.offsetTop - container.offsetHeight - 500 || pageYOffset === 0 && activated === true ) {
    //                 counters.forEach( function(counter) {
    //                     counter.innerText = 0;
    //                 } )
    //                 activated = false
    //             }

    //     })
        
    // } )

    onMounted(() => {
    // Cache the container and counters elements
    const container = document.querySelector(".counters");
    const counters = document.querySelectorAll(".counts");
    let activated = false;

    // Function to update each counter incrementally
    function updateCount(counter) {
        const target = parseInt(counter.getAttribute("data-val"));
        let count = 0;
        
        function incrementCount() {
            if (count < target) {
                count++;
                counter.innerText = count;
                setTimeout(incrementCount, 10);
            } else {
                counter.innerText = target;
            }
        }

        incrementCount();
    }

    // Scroll event listener to trigger counter updates
    window.addEventListener("scroll", () => {
        const scrollPosition = window.pageYOffset;
        const triggerPosition = container.offsetTop - container.offsetHeight - 300;
        const resetPosition = container.offsetTop - container.offsetHeight - 500;

        if (scrollPosition > triggerPosition && !activated) {
            counters.forEach(updateCount);
            activated = true;
        } else if ((scrollPosition < resetPosition || scrollPosition === 0) && activated) {
            counters.forEach(counter => counter.innerText = 0);
            activated = false;
        }
    });
});

</script>

<template>
    <section class="marketing mt-[130px] mb-[119px]">
        
        <div class="container">
            <div class="mb-[170px]">
                <div class="max-w-[1296px] mx-auto">
                    <div class=" flex gap-[134px] justify-between items-center mb-[86px]">
                        <h2 class="max-w-[620px]">
                            Take the lead in smartly social media marketing
                        </h2>
                        <p class="text-[18px] opacity-70 max-w-[526px]">
                            We offer some special services through which you can 
                            easily complete the marketing work on social media. 
                            Which helps increase your lead and sales.
                        </p>
                    </div>

                    <div class="grid grid-cols-3 gap-6 mb-[167px]">

                        <div class="px-[50px] pt-[50px] pb-[40px] border-solid border-[2px] border-[#12141D] rounded-[20px]">
                            <img class="mb-[45px]" src="../assets/images/strategy.svg" alt="strategy">
                            <h4 class="mb-5">Social Media Strategy</h4>
                            <p class="mb-10 opacity-70 ">A social media strategy is a summary of everything you 
                                plan to do and hope to achieve on social media.
                            </p>
                            <a class="gap-[9px] font-Inter font-semibold py-1" href="#">
                                <span class="text-start">Discover More</span>
                                <img class="" src="../assets/images/arrow-right.svg" alt="arrow-right">
                            </a>
                        </div>

                        <div class="px-[50px] pt-[50px] pb-[40px] border-solid border-[2px] border-[#12141D] rounded-[20px]">
                            <img class="mb-[45px]" src="../assets/images/route.svg" alt="strategy">
                            <h4 class="mb-5">Digital Marketing Plan</h4>
                            <p class="mb-10 opacity-70">A social media strategy is a summary of everything you 
                                plan to do and hope to achieve on social media.
                            </p>
                            <a class="gap-[9px] font-Inter font-semibold py-1" href="#">
                                <span class="text-start">Discover More</span>
                                <img class="" src="../assets/images/arrow-right.svg" alt="arrow-right">
                            </a>
                        </div>

                        <div class="px-[50px] pt-[50px] pb-[40px] border-solid border-[2px] border-[#12141D] rounded-[20px]">
                            <img class="mb-[45px]" src="../assets/images/search-eng.svg" alt="strategy">
                            <h4 class="mb-5">Digital Marketing Plan</h4>
                            <p class="mb-10 opacity-70">A social media strategy is a summary of everything you 
                                plan to do and hope to achieve on social media.
                            </p>
                            <a class="gap-[9px] font-Inter font-semibold py-1" href="#">
                                <span class="text-start">Discover More</span>
                                <img class="" src="../assets/images/arrow-right.svg" alt="arrow-right">
                            </a>
                        </div>
                    </div>
                </div>
                <div class="">
                    <div class="flex justify-between gap-4 mb-[110px]">
                        <div class="shrink-0">
                            <img class="w-[590px] aspect-[5.9/3.94] object-cover " src="../assets/images/users.svg" alt="users">
                        </div>
                        <div class="py-[33px] max-w-[636px]">
                            <h2 class="mb-[40px]">Bring your target users together on social media</h2>
                            <p class="opacity-70 text-[18px] mb-[40px]">
                                Social media audience research isn’t complicated. It’s mainly 
                                about narrowing your focus while expanding your reach.
                            </p>
                            <p class="opacity-70 text-[18px]">
                                We’ve created a free social media audience research 
                                template to help you keep track of all the information 
                                you learn as you conduct your research.
                            </p>
                        </div>
                    </div>
                    <div class="flex justify-between  gap-4">
                        <div class="py-[33px] max-w-[636px]">
                            <h2 class="mb-[40px]">Build your brand & reach out to social followers</h2>
                            <p class="opacity-70 text-[18px] mb-5">
                                Brand awareness is cited as the top priority for marketers, and social media 
                                channels are a one-to-many solution for getting the word out 
                                about your products and services. 
                            </p>
                            <p class="opacity-70 text-[18px]">
                                By creating a strong brand presence on social media,
                                 you can reach a broader audience & get partners 
                                 brand advocates to post content.
                            </p>
                        </div>
                        <div class="shrink-0">
                            <img class="w-[590px] aspect-[5.9/3.94] object-cover" src="../assets/images/followers.svg" alt="followers">
                        </div>
                    </div>

                </div>

            </div>
        </div>
        
        <div class="counters flex justify-between bg-[#E5EEF5] py-[80px] px-[153px] max-w-[1600px] mx-auto mb-[142px]">
            <div>
                <h2 class="text-[72px] leading-[80px] counts" data-val="15">0</h2>
                <p class="text-[18px] leading-[28px]">Years of experience</p>
            </div>
            <div>
                <h2 class="text-[72px] leading-[80px]"><span class="counts" data-val="36">0</span>k</h2>
                <p class="text-[18px] leading-[28px]">Social followers</p>
            </div>
            <div>
                <h2 class="text-[72px] leading-[80px] counts" data-val="428">0</h2>
                <p class="text-[18px] leading-[28px]">Project completed</p>
            </div>
            <div>
                <h2 class="text-[72px] leading-[80px]"><span class="counts" data-val="92">0</span>k</h2>
                <p class="text-[18px] leading-[28px]">Social profiles</p>
            </div>
        </div>

        <div class="container">
            <div class="flex justify-between  gap-4">
                <div>
                    <img class="w-[668px] aspect-[9/6] object-cover" src="../assets/images/easiestway.svg" alt="easiestway">
                </div>
                <div class="py-[11px] max-w-[526px]"> 
                    <h2 class="mb-[60px]">
                        The easiest way to promote social media
                    </h2>
                    <h4 class="leading-[1.24] text-[21px] ">
                        Build A Community
                    </h4>
                    <p class="text-[18px] leading-[1.55] opacity-70 mt-5">
                        Community building is a field of practices directed toward 
                        the creation or enhancement of community among individuals.
                    </p>
                    <h4 class="leading-[1.24] text-[21px] mt-10">
                        Video & Live Streaming
                    </h4>
                    <p class="text-[18px] leading-[1.55] opacity-70 mt-5">
                        Connect your audio and video sources. This involves on audio and video sources 
                        to your main live streaming setup.
                    </p>
                </div>
            </div>
        </div>

    </section>
</template>

<style lang="scss" scoped>

</style>