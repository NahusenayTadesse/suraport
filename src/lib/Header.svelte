
<script>

    import { ModeWatcher, toggleMode } from 'mode-watcher';
    import { Moon, Sun } from '@lucide/svelte';
    
	import { link } from './global.svelte';
	import { fly } from 'svelte/transition';
    let sections = [{ name: "Home", href: '/'},

  {name: "About", href: '#about'},
  {name: "Gallery", href: '#gallery'},
  {name: 'Contact', href: '#contact'}
    ];

    let isOpen = $state(false);

    


</script>

<ModeWatcher />

<div class="hidden lg:flex flex-row justify-between p-12 justify-self-center sticky top-0 bg-white/70 dark:bg-black/70 backdrop-blur-[5px] w-full">
    <h1 class="font-head font-bold text-2xl dark:text-white text-dark-gray"><a href="/">SURAFEL ASMAMAW</a></h1> 
   <div class="flex flex-row justify-center gap-12 font-head">
    {#each sections as section}

    <a href={section.href} class="text-dark-gray dark:text-white hover:text-brown text-xl">{section.name}</a>
    {/each}

    <button onclick={toggleMode} >
       
        <Sun class="dark:block hidden mb-2 transition-all w-[50px]" />
        <Moon class="block dark:hidden mb-2 transition-all w-[50px]" />
     
    
    </button>
    </div>
</div>


<div class="w-full lg:hidden flex flex-row justify-between items-start p-4">
     <button 
      class="text-black dark:text-white focus:outline-none" 
      onclick={() => (isOpen = !isOpen)}
      aria-label="Toggle Menu"
      aria-expanded={isOpen ? 'true' : 'false'}
    >
      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path 
          stroke-linecap="round" 
          stroke-linejoin="round" 
          stroke-width="2" 
          d={isOpen ? 'M6 18L18 6M6 6l12 12' : 'M4 6h16M4 12h16M4 18h16'} 
          aria-label="Toggle Menu"
          aria-expanded={isOpen ? 'true' : 'false'}
        />
      </svg>
    </button>
   {#if isOpen}
   <button onclick={()=>(isOpen = !isOpen)} class="fixed w-full top-0 left-0 h-full bg-black/40 dark:bg-black/60 z-30" aria-label="Menu Closer" ></button>
   
    <div class="w-[70%] flex flex-col p-12 shadow-md fixed top-0 left-0 bg-white/60 dark:bg-black/30 backdrop-blur-md h-full z-30"
    transition:fly={{x:-200, duration:600 }}> 

         <button 
      class="text-black dark:text-white focus:outline-none absolute right-2 top-4" 
      onclick={() => (isOpen = !isOpen)}
      aria-label="Toggle Menu"
      aria-expanded={isOpen ? 'true' : 'false'}
    >
      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path 
          stroke-linecap="round" 
          stroke-linejoin="round" 
          stroke-width="2" 
          d={isOpen ? 'M6 18L18 6M6 6l12 12' : 'M4 6h16M4 12h16M4 18h16'} 
          aria-label="Toggle Menu"
          aria-expanded={isOpen ? 'true' : 'false'}
        />
      </svg>
      </button>
        <div class="flex flex-col gap-8 mt-25">
        {#each sections as section}
           <a href={section.href} class="font-head text-2xl text-black dark:text-white">{section.name}</a>
        {/each}
        </div>

    </div>
    {/if}
    
    <button onclick={toggleMode} >
       
        <Sun class="dark:block hidden mb-2 transition-all w-[50px]" />
        <Moon class="block dark:hidden mb-2 transition-all w-[50px]" />
     
    
    </button>
</div>


