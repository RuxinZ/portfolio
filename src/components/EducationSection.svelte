<script lang="ts">
  import SectionDivider from "./SectionDivider.svelte";

  const educationArr = [
    {year:'2023', school:'CodeSmith', degree:'Software Engineering Residency'},
    {year:'2020', school:'Middlebury Institute of International Studies at Monterey', degree:'Master in International Education Management'},
    {year:'2018', school:'Middlebury Institute of International Studies at Monterey', degree:'Bachelor in International Studies'},
  ]

</script>
<section id="education" class="py-20 lg:py-32 flex flex-col gap-24">
  <SectionDivider title="Education"/>
  
  <div class="flex flex-col gap-20 w-full mx-auto max-w-[800px]">
    {#each educationArr as education, index}
      <div class="flex gap-6 sm:gap-8">
        <div class="w-16 text-right items-end ">
          <p  class="poppins text-4xl sm:text-5xl md:text-6xl text-slate-500 font-semibold">
            0{index + 1}
          </p>
        </div>
        <div class="flex flex-col gap-2 sm:gap-3">
            <h3 class="text-1xl sm:text-2xl md:text-3xl text-violet-400">
                {education.school}
            </h3>
            <p class="text-lg sm:text-1xl md:text-2xl"><span class="  ">{education.degree}</span>&nbsp;&nbsp;-&nbsp;&nbsp;{education.year}</p>
        </div>
      </div>
    {/each}
  </div>

</section>
