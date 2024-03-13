<!-- Circle.svelte -->
<script>
    export let size = '1/2'; // Size of the circle, default is half the screen size
  </script>
  
  <div class="fixed inset-0 flex items-center justify-center">
    <div class="absolute w-screen h-screen bg-black bg-opacity-75 backdrop-blur-lg rounded-full" style="width: calc(100vw * {{size}}); height: calc(100vh * {{size}});"></div>
  </div>
  
  <style>
    /* You can import Tailwind CSS or include it via CDN */
  </style>
  