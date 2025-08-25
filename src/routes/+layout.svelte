<script lang="ts">
  import { onMount } from 'svelte';
  import { writable } from 'svelte/store';
  import '../app.css';
  import favicon from '$lib/assets/favicon.svg';
  import Glapko from '$lib/Glapko.svelte';
  import Background from '$lib/Background.svelte';

  const Base = import.meta.env.BASE_URL;

  let { children } = $props();
</script>

<svelte:head>
  <link rel="icon" href={favicon} />
</svelte:head>

<Background />

<!-- Use Tailwind CSS to style the header and nav based on the dark mode state -->
<header class="bg-white text-black shadow-md dark:bg-[#282828] dark:text-white transition-colors duration-300">
  <nav class="container mx-auto flex justify-between items-center py-4">
    <a href="{Base}" ><Glapko/></a>
    <div class="flex items-center space-x-6">
      <a href="{Base}" class="hover:text-[#dc832e] transition-colors duration-300">Home</a>
      <a href="{Base}about" class="hover:text-[#dc832e] transition-colors duration-300">About</a>
      <a href="{Base}contact" class="hover:text-[#dc832e] transition-colors duration-300">Contact</a>
    </div>
  </nav>
</header>

<main>
  {@render children?.()}
</main>

<footer class="text-center py-4 text-gray-600 dark:text-gray-400">
  <p>&copy; 2025 GLAPKO Studios</p>
</footer>

<style>
  /* Base styles to apply the Tailwind transition */
  html {
    @apply transition-colors duration-300;
  }

  main, header {
    padding: 0 min(5%, 50px);
  }
</style>
