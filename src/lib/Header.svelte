
<script>

    import { ModeWatcher, toggleMode } from 'mode-watcher';
    import { Moon, Sun } from '@lucide/svelte';
    
	import { link } from './global.svelte';
    let sections = [{ name: "Home", href: '/'},

  {name: "About", href: '#about'},
  {name: "Gallery", href: '#gallery'},
  {name: 'Contact', href: '#contact'}
    ];


</script>
<ModeWatcher />

<div class="flex flex-row justify-between h-[10vh] p-12 justify-self-center w-[85%]">
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