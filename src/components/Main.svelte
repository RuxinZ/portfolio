<script lang="ts">
  import Step from "./Step.svelte"; 
  let steps = [
    {name: 'abc', icon:'fa-solid fa-cart-shopping', href: '', description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Adipiscing elit pellentesque habitant morbi tristique senectus et netus et. Vulputate eu scelerisque felis imperdiet proin fermentum leo vel. Neque vitae tempus quam pellentesque nec nam aliquam sem et. Varius duis at consectetur lorem donec.'},
    {name: 'def', icon:'fa-solid fa-list-check', href: '', description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Gravida quis blandit turpis cursus in hac habitasse platea. Fermentum dui faucibus in ornare. Tellus in metus vulputate eu scelerisque felis imperdiet proin fermentum.'},
    {name: 'zxy', icon:'fa-solid fa-diagram-project', href: '', description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Sed risus ultricies tristique nulla aliquet enim. Egestas tellus rutrum tellus pellentesque eu tincidunt tortor aliquam nulla.'},
  ]

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
          class="object-cover z-[2] max-h-[70vh]"
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

</main>