<!-- src/lib/Background.svelte -->
<div class="bg"></div>

<style>
  .bg {
    position: fixed;
    inset: 0;
    background: #35383b; /* základní tmavé pozadí */
    z-index: -1;
    overflow: hidden;
  }

  .bg::before {
    content: "";
    position: absolute;
    inset: -20%;
    background:
      radial-gradient(60vmax 60vmax at 15% 20%, #2d59d6 0 35%, transparent 60%),
      radial-gradient(50vmax 50vmax at 75% 15%, #dc832e 0 30%, transparent 60%),
      radial-gradient(70vmax 70vmax at 30% 80%, #2d59d6 0 28%, transparent 60%),
      radial-gradient(60vmax 60vmax at 85% 70%, #dc832e 0 32%, transparent 60%);
    filter: blur(60px) saturate(120%);
    opacity: .1;
    pointer-events: none;
  }
</style>
