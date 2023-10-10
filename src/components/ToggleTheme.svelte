<script lang="ts">
  import theme from '$lib/stores/theme';

  $: themeIsLight = $theme === 'light';
  const toggleTheme = () => {
    console.log(themeIsLight)
    themeIsLight = !themeIsLight;
    console.log(themeIsLight)
  }

</script>


<div>
  <button on:click={toggleTheme}>
    <i class={"fa-regular fa-sun " + `${themeIsLight ? 'visually-hidden ' : ''}`}></i> 
    <i class={"fa-solid fa-moon " + `${!themeIsLight ? 'visually-hidden ' : ''}`}></i> 
  </button>
   
</div>