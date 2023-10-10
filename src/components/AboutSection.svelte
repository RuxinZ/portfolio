<script lang="ts">
   import ScrollingText from "./ScrollingText.svelte";
  const benefits = [
        {
            name: "a self taught developer",
            description:
                "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Adipiscing elit pellentesque habitant morbi tristique senectus et netus et. Vulputate eu scelerisque felis imperdiet proin fermentum leo vel. Neque vitae tempus quam pellentesque nec nam aliquam sem et. Varius duis at consectetur lorem donec.",
        },
        {
            name: "a life-long learner",
            description:
                "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Sed risus ultricies tristique nulla aliquet enim. Egestas tellus rutrum tellus pellentesque eu tincidunt tortor aliquam nulla.",
        },
        {
            name: "an excellent communicator",
            description:
                "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Gravida quis blandit turpis cursus in hac habitasse platea. Fermentum dui faucibus in ornare. Tellus in metus vulputate eu scelerisque felis imperdiet proin fermentum.",
        },
    ];

  const candidates = [
    [false, false, true, true],
    [true, true, true, false],
    [false, true, false, true], 
    [true, true, true, true] 
  ]
  const qualifications = ['Dedication', 'Critical Thinking', 'Interpersonal Skills', 'Programming Ability']

</script>

<section id="aboutme" class="py-20 pt-10 lg:pt-16 lg:py-32 flex flex-col gap-16 sm:gap-20 md:gap-24 relative">
  <div
  class="flex flex-col gap-2 text-center relative before:absolute before:top-0 before:left-0 before:w-2/3 before:h-1.5 before:bg-violet-700 after:absolute after:bottom-0 after:right-0 after:w-2/3 after:h-1.5 after:bg-violet-700 py-4"
  >
      <h6 class="text-large sm:text-xl md:text-2xl">
          Want to know more?
      </h6>
      <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
          A bit <span class="poppins text-violet-400">about</span> me.
      </h3>
  </div>
  <p class="mx-auto poppins font-semibold text-lg sm:text-xl md:text-2xl">
    I am . . .
  </p>
  <div class="flex flex-col gap-20 w-full mx-auto max-w-[800px]">
    {#each benefits as benefit, index}
      <div class="flex gap-6 sm:gap-8">
        <p
            class="poppins text-4xl sm:text-5xl md:text-6xl text-slate-500 font-semibold"
        >
            0{index + 1}
        </p>
        <div class="flex flex-col gap-6 sm:gap-8">
            <h3 class="text-2xl sm:text-3xl md:text-5xl">
                {benefit.name}
            </h3>
            <p>{benefit.description}</p>
        </div>
      </div>
    {/each}
  </div>
  <ScrollingText/>
  <h5 class={" text-2xl sm:text-3xl font-semibold text-center poppins "}>
    The <span class="text-violet-400">Complete</span> Package
  </h5>
<div
    class="flex flex-col overflow-x-auto gap-10 max-w-[800px] mx-auto w-full"
>
  <table class="bg-white text-slate-700 rounded text-center">
    <thead class={"border-b border-solid border-slate-200  "}>  
      <tr class="">
          <th />
          {#each Array(3) as _, index}
          <th class="whitespace-nowrap p-2 px-4">Candidate #{index+1}</th>
          {/each}

          <th class="bg-violet-700 text-white whitespace-nowrap p-4 px-8">Me</th>
      </tr>
    </thead>
    <tbody>
      {#each qualifications as qualification, qualification_index}
        <tr class="border-b border-solid border-slate-200">
          <td
              class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm"
              >{qualification}</td
          >
          {#each Array(4) as _, candidate_index}
       
          <td><i class={`fa-solid fa-${candidates[candidate_index][qualification_index] ? 'check' : 'xmark'} text-${candidate_index === 3 ? 'green': 'slate'}-500`} /></td>
          {/each}
        </tr>
      {/each}
      <tr class="border-b border-solid border-slate-200">
        <td
            class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm"
            >Dedication</td
        >
        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
        <td><i class="fa-solid fa-check text-slate-500" /></td>
        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
        <td><i class="fa-solid fa-check text-green-500" /></td>
    </tr>

    </tbody>
  </table>
</div>
<div class="mx-auto -mt-12 italic sm:hidden opacity-50">
    <p>Scroll to see more &rarr;</p>
</div>
<p class="mx-auto text-2xl">So why not invest?</p>
</section>