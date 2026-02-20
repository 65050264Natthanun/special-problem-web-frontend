<script lang="ts">
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher<{
        search: string; 
    }>();

    export let value: string = ""; 
    export let placeholder: string = "ค้นหาชื่อปัญหาพิเศษ หรือรหัสนักศึกษาผู้จัดทำ..";

    function handleSubmit(): void {
        // ป้องกันการส่งค่าว่าง
        if (!value.trim()) return;
        
        dispatch('search', value);
    }

</script>

<form on:submit|preventDefault={handleSubmit} 
    class="relative w-full max-w-xl flex items-center gap-2 group ">

    <div class="relative flex-1">
        <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
            <svg class="w-5 h-5 text-gray-500 group-focus-within:text-gray-300 transition-colors" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
            </svg>
        </div>

        <input type="search"
        bind:value
        {placeholder}
        class="block w-full p-3 pl-10 text-sm text-gray-300 border border-white rounded-lg bg-white 
                focus:ring-2 focus:ring-gray-400 focus:border-gray-400 outline-none transition-all shadow-sm"
        />
    </div>

    <button
        type="submit"
        class="px-5 py-3 text-sm font-medium text-white bg-blue-600 rounded-lg hover:bg-blue-700 
            focus:ring-4 focus:outline-none focus:ring-blue-300 transition-all shadow-md active:scale-95">
        ค้นหา
    </button>
</form>