<script>
  import '~/app.css'
</script>

<svelte:head>
  <script>
    if (document) {
      let mode = localStorage.theme || 'light'
      if (mode === 'dark' || window.matchMedia('(prefers-color-scheme: dark)').matches) {
        document.documentElement.classList.add('dark')
        localStorage.theme = 'dark'
      } else {
        document.documentElement.classList.remove('dark')
        localStorage.theme = 'light'
      }
    }
  </script>
</svelte:head>

<slot />
