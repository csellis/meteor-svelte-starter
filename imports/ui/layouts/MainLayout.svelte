<script>
  import { Link } from "svelte-routing";
  import MobileMenu from "../components/MobileMenu";
  import SideBar from "../components/SideBar";

  export let menuOpen = false;

  function toggleMenu(event) {
    menuOpen = !menuOpen;
    // console.log(menuOpen);
  }
</script>

<div class="h-screen flex overflow-hidden bg-gray-100">

  <MobileMenu {menuOpen} {toggleMenu} />

  <div class="flex flex-col w-0 flex-1 overflow-hidden">
    <div class="md:hidden pl-1 pt-1 sm:pl-3 sm:pt-3">
      <button
        on:click={toggleMenu}
        class="-ml-0.5 -mt-0.5 h-12 w-12 inline-flex items-center justify-center
        rounded-md text-gray-500 hover:text-gray-900 focus:outline-none
        focus:ring-2 focus:ring-inset focus:ring-indigo-500 ">
        <span class="sr-only">Open sidebar</span>
        <!-- Heroicon name: menu -->
        <svg
          class="h-6 w-6"
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
          aria-hidden="true">
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16" />
        </svg>
      </button>
    </div>

    <main
      class="flex-1 relative z-0 overflow-y-auto focus:outline-none"
      tabindex="0">
      <div class="py-6">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 md:px-8">
          <h1 class="text-2xl font-semibold text-gray-900">Dashboard</h1>
        </div>
        <div class="max-w-7xl mx-auto px-4 sm:px-6 md:px-8">
          <!-- Replace with your content -->
          <div class="py-4">
            <slot />
          </div>
          <!-- /End replace -->
        </div>
      </div>
    </main>
  </div>

</div>
