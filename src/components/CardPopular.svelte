<script>
    // กำหนดตัวแปรสำหรับข้อมูล (Mock data)
    let category = "ปัญหาพิเศษ";
    let titleThai = "ชื่อโปรเจคภาษาไทย";
    let titleEnglish = "ชื่อโปรเจคภาษาอังกฤษ";
    let keywords = ["คำสำคัญ", "คำสำคัญ"];
</script>

<div class="w-full max-w-60 h-full max-h-80 bg-white rounded-xl border border-gray-200 shadow-sm px-5 py-4 flex flex-col gap-4">
    <div class="pb-3 border-b border-gray-500">
        <h5 class="text-black">
            {category}
        </h5>
    </div>

    <div class="w-full h-full flex flex-col gap-2">
        <p class="text-black">
            {titleThai}
        </p>
        <p class="text-black">
            {titleEnglish}
        </p>
    </div>

    <hr class="border-gray-500" />

    <div class="flex flex-col gap-2">
        {#each keywords as keyword}
            <h5 class="text-gray-800 text-base">
                {keyword}
            </h5>
        {/each}
    </div>

    <div class="h-24"></div>

</div>