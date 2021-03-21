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
                        <th class="w-1/12"><a target="_blank" href="https:/google.com"  @mouseover="hover = true" @mouseleave="hover = false" class="inline-block relative focus:outline-none w-full flex items-center justify-center">
                            <svg v-tooltip.top-center="msg" class="cursor-not-allowed fill-current w-7 h-7 text-gray-500" viewBox="0 0 23 19" xmlns="http://www.w3.org/2000/svg">
                            <path d="M22.1303 9.19252C20.059 4.23267 15.9584 0.876892 11.2632 0.876892C6.56793 0.876892 2.46622 4.23502 0.39608 9.19299C0.308707 9.4051 0.263184 9.63945 0.263184 9.87713C0.263184 10.1148 0.308707 10.3492 0.39608 10.5613C2.46737 15.5211 6.56793 18.8769 11.2632 18.8769C15.9584 18.8769 20.0601 15.5188 22.1303 10.5608C22.2177 10.3487 22.2632 10.1143 22.2632 9.87666C22.2632 9.63898 22.2177 9.40463 22.1303 9.19252ZM11.2632 16.6269C10.1754 16.6269 9.11201 16.231 8.20754 15.4893C7.30307 14.7476 6.59812 13.6934 6.18184 12.46C5.76555 11.2266 5.65664 9.8694 5.86885 8.56003C6.08107 7.25066 6.6049 6.04793 7.37409 5.10392C8.14328 4.15992 9.12329 3.51704 10.1902 3.25659C11.2571 2.99614 12.363 3.12981 13.3679 3.64071C14.3729 4.1516 15.2319 5.01676 15.8363 6.12679C16.4406 7.23682 16.7632 8.54187 16.7632 9.87689C16.7635 10.7634 16.6215 11.6414 16.3452 12.4605C16.069 13.2797 15.6639 14.0239 15.1531 14.6508C14.6423 15.2777 14.0358 15.7749 13.3684 16.114C12.7009 16.453 11.9856 16.6273 11.2632 16.6269ZM11.2632 5.37689C10.9359 5.38251 10.6107 5.44226 10.2965 5.55455C10.5555 5.98658 10.6798 6.51825 10.6469 7.05312C10.6139 7.58799 10.4258 8.09065 10.1168 8.46994C9.80772 8.84923 9.39815 9.08004 8.96233 9.1205C8.5265 9.16096 8.0933 9.0084 7.74127 8.69049C7.54081 9.59686 7.577 10.5576 7.84473 11.4374C8.11246 12.3172 8.59827 13.0718 9.23376 13.595C9.86925 14.1182 10.6224 14.3837 11.3873 14.354C12.1522 14.3244 12.8902 14.0011 13.4975 13.4297C14.1048 12.8583 14.5509 12.0676 14.7728 11.1688C14.9948 10.27 14.9815 9.30838 14.7348 8.41935C14.4881 7.53031 14.0205 6.7586 13.3977 6.21282C12.775 5.66704 12.0284 5.37468 11.2632 5.37689Z"/>
                            </svg>
                            </a></th>
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
        post_data: {},
        temp: {},
        token: "thisisspecialsecreattokenfordemo:)",
        row_data: [{ id:1, key:'', value: ''},],
        isActive: false,
        hover: false,
        msg: "This is not avtive."
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
            if (this.isActive) {
                console.log(this.row_data[id])
            }
        },

        saveData() {
            this.is_saved = true
            this.isActive = true
            console.log(this.row_data)
            for (const i in this.row_data) {
                console.log("DEBUG: ", this.row_data[i])
                    this.temp[this.row_data[i].key] = this.row_data[i].value
                    console.log("temp", this.temp)
            }
            console.log("Final Data: ", JSON.stringify(this.temp))
            // console.log(JSON.parse(JSON.stringify(this.row_data)))
            // fetch("http://127.0.0.1:8000/", { 
                
            //     // Adding method type 
            //     method: "POST", 
                
            //     // Adding body or contents to send 
            //     body: JSON.stringify({
            //                 token: this.token,
            //                 payload: {data: this.row_data}
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

.show {
    @apply inline-block;
}

</style>