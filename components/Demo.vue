<template>
    <div class="container mx-auto">
        <div class="border-2 border-solid border-gray-700 rounded-lg p-4 py-20 lg:px-32 md:px-12">
            <div class="flex justify-between px-10">
                <div></div>
                <div class="inline-block lg:space-x-6 sm:space-x-2">
                    <input disabled=true class="py-2 px-4 rounded-lg text-gray-700 text-sm w-72 placeholder-gray-400 font-semibold" placeholder="Your secret access token here." type="text" name="token" value="thisisspecialsecreattokenfordemo:)">
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
                    <tr v-for="row in row_data" :key="row.id" class="">
                        <th class="w-3/12 sm:px-1 lg:px-4"><input v-model="row.key" class="w-full sm:px-1 lg:px-2 py-1 rounded-md" type="text"></th> {{row.id}}
                        <th class="w-6/12 sm:px-1 lg:px-4"><input v-model="row.value"  class="w-full sm:px-1 lg:px-2 py-1 rounded-md" type="text"></th>
                        <th class="w-1/12"><button v-on:click="singelView(row.id)" class="focus:outline-none w-full flex items-center justify-center"><img class="w-7 h-7" src="@/assets/eye.svg" alt="Delete Button"></button></th>
                        <th class="w-1/12"><button class="focus:outline-none w-full flex items-center justify-center"><img class="w-7 h-7" src="@/assets/link.svg" alt="Delete Button"></button></th>
                        <th class="w-1/12"><button v-on:click="deleteRow(row.id)" class="focus:outline-none w-full flex items-center justify-center"><img class="w-7 h-7" src="@/assets/delete.svg" alt="Delete Button"></button></th>

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
                <button v-on:click="addNewRow" class="p-3 focus:outline-none"><img src="@/assets/plus.svg" alt="Add more"></button>
                <button class="flex items-center justify-around bg-green-600 px-4 py-2 rounded-md">
                    <span v-on:click="saveData" class="text-white uppercase px-2">Save</span>
                    <img src="@/assets/save.svg" alt="Add more">
                </button>
            </div>
        </div>


    </div>
</template>

<script>

export default {
    data() {
        return {
        id: 2,
        key: '',
        value: '',
        is_saved: false,
        token: "thisisspecialsecreattokenfordemo:)",
        row_data: [{ id:1, key:'', value: ''},]
        }
    },
    methods: {
        addNewRow() {
            let my_obj = {
                id: this.id,
                key: this.key,
                value: this.value,
            }
            this.row_data.push(my_obj)
            this.id++;
            this.key = ''
            this.value = ''
        },

        deleteRow(id) {
            console.log("Deleting row")
            console.log(id)
            this.row_data = this.row_data.filter(row => row.id !== id)

        },

        singelView(id) {
            console.log(this.row_data[id])
        },

        saveData() {
            this.is_saved = true
            console.log(Object.values(this.row_data))
            // fetch("http://127.0.0.1:8000/", { 
                
            //     // Adding method type 
            //     method: "POST", 
                
            //     // Adding body or contents to send 
            //     body: JSON.stringify({
            //                 token: this.token,
            //                 payload: this.row_data
            //         }),
                
            //     // Adding headers to the request 
            //     headers: { 
            //         "Content-type": "application/json; charset=UTF-8"
            //     } 
            // }) 
            
            // // Converting to JSON 
            // .then(response => response.json()) 
            
            // // Displaying results to console 
            // .then(json => console.log(json)); 
        }
    }
}
</script>

<style scoped>
table {
    border-collapse: separate;
    border-spacing: 0 1.3rem;
}

</style>