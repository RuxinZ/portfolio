<script lang="ts">
  export let subtitle: string;
  export let title: string;
</script>

<div
class="flex flex-col gap-2 text-center relative before:absolute before:top-0 before:left-0 before:w-2/3 before:h-1.5 before:bg-violet-700 after:absolute after:bottom-0 after:right-0 after:w-2/3 after:h-1.5 after:bg-violet-700 py-4"
>
    {#if subtitle}
      <h6 class="text-large sm:text-xl md:text-2xl ">
          {subtitle}
      </h6>
    {/if}
    <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
        {title}
    </h3>
</div>