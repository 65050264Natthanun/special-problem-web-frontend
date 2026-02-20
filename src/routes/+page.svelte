<script lang="ts">
	import kmitlLogo from '$lib/assets/Kmitl-logo-navbar.png';
	import SearchBar from '../components/SearchBar.svelte';
	import CardPopular from '../components/CardPopular.svelte';
	import Button from '../components/Button.svelte';

	let searchTerm: string = "";

	// ฟังก์ชันรองรับการค้นหา
	async function handleSearch(event: CustomEvent<string>): Promise<void> {
		const query = event.detail; // TypeScript จะรู้ทันทีว่า query คือ string
		
		console.log("Searching for:", query);
		
		// ตัวอย่างการเตรียมยิง API ไปที่ FastAPI
		try {
		// const response = await fetch(`http://localhost:8000/search?q=${query}`);
		// const data = await response.json();
		// console.log(data);
		} catch (error) {
		console.error("Search failed:", error);
		}
	}

</script>

<main class="min-h-screen bg-orange-500 flex flex-col items-center w-screen overflow-x-hidden">
	<div class="w-full bg-linear-to-b from-orange-500 to-orange-700 gap-7 pt-8 pb-12 px-4 sm:px-6 md:px-10 flex flex-col items-center">
		<img src={kmitlLogo} alt="KMITL Logo" class="h-35 md:h-42 lg:h-50"/>
		<h3 class="text-white">ค้นหาเล่มปัญหาพิเศษ</h3>
		<SearchBar bind:value={searchTerm} on:search={handleSearch} />
	</div>
	
	<div class="w-full bg-white gap-12 px-4 sm:px-6 md:px-10 lg:px-16 py-10 flex flex-col">
		<h3 class="text-black">ปัญหาพิเศษที่กำลังเป็นที่สนใจ</h3>
		<CardPopular />
	</div>


</main>
