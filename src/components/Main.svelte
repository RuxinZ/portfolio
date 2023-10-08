<script lang="ts">
  import Step from "./Step.svelte"; 
  const steps = [
    {name: 'abc', icon:'fa-solid fa-cart-shopping', href: '', description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Adipiscing elit pellentesque habitant morbi tristique senectus et netus et. Vulputate eu scelerisque felis imperdiet proin fermentum leo vel. Neque vitae tempus quam pellentesque nec nam aliquam sem et. Varius duis at consectetur lorem donec.'},
    {name: 'def', icon:'fa-solid fa-list-check', href: '', description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Gravida quis blandit turpis cursus in hac habitasse platea. Fermentum dui faucibus in ornare. Tellus in metus vulputate eu scelerisque felis imperdiet proin fermentum.'},
    {name: 'zxy', icon:'fa-solid fa-diagram-project', href: '', description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Sed risus ultricies tristique nulla aliquet enim. Egestas tellus rutrum tellus pellentesque eu tincidunt tortor aliquam nulla.'},
  ]

  const benefits = [
        {
            metric: "10x",
            name: "a self taught developer",
            description:
                "I taught myself to code using free online resources and absolutely fell in love with the creativity and problem solving that is involved in developing and engineering innovative new online experiences. Starting of with JavaScript, HTML & CSS and evolving my knowledge base to include JavaScript frameworks, backend programming, design, cloud services and much much more.",
        },
        {
            name: "a product design & UX finatic",
            description:
                "Carefully crafting and designing amazing user experiences allows me to express and experiment with every morsel of creativity I have. I love the challenge of learning new design concepts and enabling users with amazing online experiences.",
        },
        {
            name: "an excellent communicator",
            description:
                "Communication is key and it's a paramount value of mine. I believe in transparency and constructive communication above all else. This helps me develop deep relationships and ensures my effectiveness and productivity in any work space with any team.",
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

<main class="flex flex-col flex-1 p-4">
  <!-- Intro Section -->
  <section 
    id="introPage" 
    class='grid grid-cols-1 lg:grid-cols-2 gap-10 py-8 sm:py-14'
  >
    <div 
      class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10"
    >
      <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
        Hi! I'm <span class="poppins text-violet-400">Carolyn</span> Zheng
        <br />Full Stack
        <span class="poppins text-violet-400">Developer</span>
      </h2>
      <p class="text-base sm:text-lg md:text-xl">
        My <span class="text-violet-400"> favorite tech</span> includes JavaScript, TypeScript, React, Svelte, Node.js + Express & PostgreSQL
        or MongoDB!
      </p>
      <button
        class="blueShadow mx-auto lg:mr-auto lg:ml-0 text-base sm:text-lg md:text-xl poppins relative overflow-hidden px-6 py-3 group rounded-full bg-white text-slate-950"
      >
          <div
              class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"
          />
          <h4 class="relative z-9">Get in touch &rarr;</h4>
      </button>
    </div>
    <div class="relative shadow-2xl grid place-items-center">
      <img
          src={"images/profile.png"}
          alt="profile"
          class="object-cover z-[2] max-h-[30vh] sm:max-h-[50vh]"
      />
    </div>

  </section>

   <!-- Projects Section -->
  <section id="projects" class="py-20 lg:py-32 flex flex-col gap-24">
    <div class="flex flex-col gap-2 text-center">
      <h6 class="text-large sm:text-xl md:text-2xl">
          A few of my creative endeavors.
      </h6>
      <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
          Curious to <span class="poppins text-violet-400">see</span> my work?
      </h3>
    </div>
    <a
        href="https://github.com/RuxinZ"
        target="_blank"
        class="mx-auto px-4 py-2 rounded-md border border-solid border-white flex items-center gap-2 -mb-4 sm:-mb-0 -mt-10 hover:border-violet-700 duration-200"
    >
        <i class="fa-regular fa-circle-play" />
        <p>Watch the video</p>
    </a>
    <div class="grid grid-cols-1 lg:grid-cols-3 gap-12 lg:gap-10">
      {#each steps as step, index}
        <Step step={step} >
          <p>{step.description}</p>
        </Step>
      {/each}
    </div>
  </section>
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
  <p class="mx-auto">So why not invest?</p>
  </section>

</main>