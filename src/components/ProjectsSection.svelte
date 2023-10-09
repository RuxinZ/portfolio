<script lang="ts">
  import Step from "./Step.svelte"; 
  const steps = [
    {name: 'abc', icon:'fa-solid fa-cart-shopping', href: '', description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Adipiscing elit pellentesque habitant morbi tristique senectus et netus et. Vulputate eu scelerisque felis imperdiet proin fermentum leo vel. Neque vitae tempus quam pellentesque nec nam aliquam sem et. Varius duis at consectetur lorem donec.'},
    {name: 'def', icon:'fa-solid fa-list-check', href: '', description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Gravida quis blandit turpis cursus in hac habitasse platea. Fermentum dui faucibus in ornare. Tellus in metus vulputate eu scelerisque felis imperdiet proin fermentum.'},
    {name: 'zxy', icon:'fa-solid fa-diagram-project', href: '', description:'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Sed risus ultricies tristique nulla aliquet enim. Egestas tellus rutrum tellus pellentesque eu tincidunt tortor aliquam nulla.'},
  ]
</script>

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