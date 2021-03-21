<template>
    <div class="container mx-auto">
        <div class="border-2 border-solid border-gray-700 rounded-lg p-4 py-20 lg:px-32 md:px-12">
            <div class="flex justify-between px-10">
                <div></div>
                <div class="inline-block lg:space-x-6 sm:space-x-2">
                    <input class="py-2 px-4 rounded-lg text-gray-700 text-sm w-72 placeholder-gray-400 font-semibold" placeholder="Your secret access token here." type="text" name="token">
                    <button class="inline-block bg-white uppercase text-gray-700 text-sm font-semibold px-4 py-2 rounded-lg">Copy Json Url</button>
                    <button class="inline-block bg-green-600 uppercase text-white text-sm font-semibold px-4 py-2 rounded-lg">Save</button>
                </div>
            </div>

            <table class="w-full">
                <thead>
                    <tr class="text-white text-xl text-left">
                        <th class="pl-6 mb-8">Name</th>
                        <th class="pl-6 mb-8">Value</th>
                    </tr>
                </thead>
                <tbody class="">
                    <tr class="">
                        <th class="w-3/12 sm:px-1 lg:px-4"><input class="w-full sm:px-1 lg:px-2 py-1 rounded-md" type="text"></th>
                        <th class="w-6/12 sm:px-1 lg:px-4"><input class="w-full sm:px-1 lg:px-2 py-1 rounded-md" type="text"></th>
                        <th class="w-1/12"><button class=" w-full flex items-center justify-center"><img class="w-7 h-7" src="@/assets/eye.svg" alt="Delete Button"></button></th>
                        <th class="w-1/12"><button class=" w-full flex items-center justify-center"><img class="w-7 h-7" src="@/assets/link.svg" alt="Delete Button"></button></th>
                        <th class="w-1/12"><button class=" w-full flex items-center justify-center"><img class="w-7 h-7" src="@/assets/delete.svg" alt="Delete Button"></button></th>

                    </tr>

                    <!-- <tr class="">
                        <th class="w-4/12 px-4"><input class="w-full px-2 py-1 rounded-md" type="text"></th>
                        <th class="w-7/12 px-4"><input class="w-full px-2 py-1 rounded-md" type="text"></th>
                        <th class="w-1/12"><button class=" w-full flex items-center justify-center"><img class="w-7 h-7" src="@/assets/delete.svg" alt="Delete Button"></button></th>
                    </tr>
                    <tr class="">
                        <th class="w-4/12 px-4"><input class="w-full px-2 py-1 rounded-md" type="text"></th>
                        <th class="w-7/12 px-4"><input class="w-full px-2 py-1 rounded-md" type="text"></th>
                        <th class="w-1/12"><button class=" w-full flex items-center justify-center"><img class="w-7 h-7" src="@/assets/delete.svg" alt="Delete Button"></button></th>
                    </tr> -->
                </tbody>
            </table>
            <div class="flex items-center justify-between pr-10 mt-8">
                <button class="p-3"><img src="@/assets/plus.svg" alt="Add more"></button>
                <button class="flex items-center justify-around bg-green-600 px-4 py-2 rounded-md">
                    <span class="text-white uppercase px-2">Save</span>
                    <img src="@/assets/save.svg" alt="Add more">
                </button>
            </div>
        </div>


    </div>
</template>

<style scoped>
table {
    border-collapse: separate;
    border-spacing: 0 1.3rem;
}
</style>