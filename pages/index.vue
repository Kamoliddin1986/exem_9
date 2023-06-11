<template lang="">
    <div class="bg-white mt-[50px] w-[100%] h-[112px] rounded-[10px] flex items-center">
        <div class="m-[24px] flex justify-around items-center ">

            <div class="h-[71px] w-[165px]">
                <h1 class="text-center font-[700] text-[28px] text-[#8A92A6]">750K</h1>
                <p class="text-center text-[#8A92A6]">Sale</p>
            </div>
            <div class="w-0 h-[62px] border border-grey-400 mx-[48px]"></div>
            
            <div class="h-[71px] w-[187px]">
                <h1 class="text-center font-[700] text-[28px] text-[#8A92A6]">7,500</h1>
                <p class="text-center text-[#8A92A6]">Cancels</p>
            </div>
            <div class="w-0 h-[60px] border border-grey-400 mx-[48px]"></div>
            
            <div class="h-[71px] w-[187px]">
                <h1 class="text-center font-[700] text-[28px] text-[#8A92A6]">7,500</h1>
                <p class="text-center text-[#8A92A6]">Total Earned</p>
            </div>
            <div class="w-0 h-[62px] border border-grey-400 mx-[48px]"></div>
            
            <div class="h-[71px] w-[187px]">
                <h1 class="text-center font-[700] text-[28px] text-[#8A92A6]">7,500</h1>
                <p class="text-center text-[#8A92A6]">Distributions</p>
            </div>
            
        </div>
    </div>

    <div class=" w-[100%] flex justify-between mt-[52px]">
        <div class="flex gap-[12px] items-center">

            <button class="w-[99px] h-[40px] rounded-[8px] bg-white border border-grey-400 text-[#344054]"> <Icon name="ic:sharp-filter-list"  class="text-[#344054]"/> Filter</button>
            <button @click="toggleModal" class="w-[114px] h-[40px] text-white text-[14px] bg-[#000AFF] rounded-[8px]"> <Icon name="ic:outline-add"  class="text-white text-[16px]"/> Add User</button>
            <p class="text-[15px] font-[700] text-[#101828]">1 row selected</p>
        </div>
        
        <div >

            <input type="serch" name="" id="" placeholder="Search" class="w-[320px] h-[44px] border border-grey-400 rounded-[10px] pl-[20px]">
        </div>
    
    </div>

    <div class="flex mt-[19px] w-[100%] h-[60px] border border-[#EAECF0] rounded-t-[8px] bg-[#F9FAFB] items-center">
        <div class="mx-[20px]">
            <input type="checkbox" class="w-[20px] h-[20px] ">
        </div>
        <div class="w-[22%] h-[28px]">
            <span class="text-[12px] font-[700] text-[#8A92A6]">Learners</span>
            <Icon name="mdi:arrow-down-thin"  class="black text-[#8A92A6]"/>
        </div>
        <div class="w-[14%] h-[28px]">
            <span class="text-[12px] font-[700] text-[#8A92A6]">Language</span>
            <Icon name="mdi:arrow-down-thin"  class="black text-[#8A92A6]"/>
        </div>
        <div class="w-[14%] h-[28px]">
            <span class="text-[12px] font-[700] text-[#8A92A6]">Occupation</span>
            <Icon name="mdi:arrow-down-thin"  class="black text-[#8A92A6]"/>
        </div>
        <div class="w-[14%] h-[28px]">
            <span class="text-[12px] font-[700] text-[#8A92A6]">Objective</span>
            <Icon name="mdi:arrow-down-thin"  class="black text-[#8A92A6]"/>
        </div>
        <div class="w-[14%] h-[28px]">
            <span class="text-[12px] font-[700] text-[#8A92A6]">Subscription</span>
            <Icon name="mdi:arrow-down-thin"  class="black text-[#8A92A6]"/>
        </div>
        <div>
        </div>
    </div>
    <!-- Users render part start -->

    <div v-for="(el,ind) in list" :key="ind" class="flex  w-[100%] h-[80px] border border-[#EAECF0] bg-white items-center ">
        <div class="mx-[20px]">
            <input type="checkbox" class="w-[20px] h-[20px] ">
        </div>
        <div class="w-[22%] h-[28px] flex items-center gap-[12px]">
            <div>
                <img :src="el.image" alt="" class="w-[40px] h-[40px]">
            </div>
            <div>
                <div class="flex items-center gap-[2px]">
                    <h1 class="text-[15px] font-[700] text-[#101828]">{{el.firstName}} {{el.lastName}}</h1>
                    <img :src="el.country" alt="" class="w-[13px] h-[10px]">
                </div>
                <p class="text-[14px] font-[700] text-[#667085]">{{el.email}}</p>
            </div>
        </div>
        <div class="w-[14%] h-[28px]">
            <p class="text-[16px] font-[700] text-[#232D42] ml-[12px]">{{el.language}}</p>
        </div>
        <div class="w-[14%] h-[28px]">
            <p class="text-[16px] font-[700] text-[#232D42] ml-[22px]">{{el.occupation}}</p>
        </div>
        <div class="w-[14%] h-[28px]">
            <p class="text-[16px] font-[700] text-[#232D42] ml-[30px]">{{el.objective}}</p>
        </div>
        <div class="w-[14%] h-[28px]">
            <p class="text-[16px] font-[700] text-[#232D42] ml-[38px]">{{el.subscription}}</p>
        </div>
        <div class="w-[22%] h-[28px] flex justify-center gap-[16px]">
            <Icon @click="deleteUser(el.id)" name="ic:twotone-delete"  class="#667085" size="24px"/>
            <Icon @click="updateModalFunc(el)" name="ic:outline-mode-edit-outline"  class="#667085" size="24px"/>
        </div>
        <div>
        </div>
    </div>

    <!-- Users render part end-->

    <div class="flex justify-between  w-[100%] h-[80px] border border-[#EAECF0] bg-white items-center px-[24px] mb-[123px] rounded-b-[8px]">
        <button @click="minus()" class="w-[86px] h-[36px] text-[14px] text-[#344054] font-[500] border border-grey-300 rounded-[8px]">Previous</button>
        <p class="text-[14px] font-[500] text-[#344054]">Page {{page}} of {{pages}}</p>
        <button @click="add()" class="w-[60px] h-[36px] text-[14px] text-[#344054] font-[500] border border-grey-300 rounded-[8px]">Next</button>
    </div>



        <!----------------------- Add user MODAL  ---------------------------->

    <!-- Main modal -->
    <div
      tabindex="-1"
      aria-hidden="true"
      :class="
        Modal
          ? 'overflow-y-auto bg-grey-200 flex overflow-x-hidden fixed top-0 right-0 left-0 z-50 justify-center items-center w-full md:inset-0 h-modal md:h-full'
          : 'hidden'
      "
    >
      <div class="relative p-4 w-full max-w-2xl h-full md:h-auto">
        <!-- Modal content -->
        <div class="relative p-4 bg-white rounded-lg shadow dark:bg-gray-800 sm:p-5">
          <!-- Modal header -->
          <div
            class="flex justify-between items-center pb-4 mb-4 rounded-t border-b sm:mb-5 dark:border-gray-600"
          >
            <h3 class="text-lg font-semibold text-gray-900 dark:text-white">
              Add new user
            </h3>
            <button
              @click="toggleModal"
              type="button"
              class="text-gray-400 bg-transparent hover:bg-gray-200 hover:text-gray-900 rounded-lg text-sm p-1.5 ml-auto inline-flex items-center dark:hover:bg-gray-600 dark:hover:text-white"
            >
              <svg
                aria-hidden="true"
                class="w-5 h-5"
                fill="currentColor"
                viewBox="0 0 20 20"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                  clip-rule="evenodd"
                ></path>
              </svg>
              <span class="sr-only">Close modal</span>
            </button>
          </div>
          <!-- Modal body -->
          <form @submit.prevent="addUser" class="w-[100%]">
            <div class="grid gap-4 mb-4 sm:grid-cols-2">
              <div>
                <label
                  for="name"
                  class="block mb-2 text-[13px] font-[700] text-[#515050] dark:text-white"
                  >First Name</label
                >
                <input
                  v-model="user.firstName"
                  type="text"
                  name="name"
                  id="name"
                  class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-600 focus:border-blue-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                  placeholder="First Name"
                  required=""
                />
              </div>

              <div>
                <label
                  for="brand"
                  class="block mb-2 text-[13px] font-[700] text-[#515050] dark:text-white"
                  >Last Name</label
                >
                <input
                  v-model="user.lastName"
                  type="text"
                  name="brand"
                  id="brand"
                  class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-600 focus:border-blue-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                  placeholder="Last name"
                  required=""
                />
              </div>
              <div>
                <label
                  for="price"
                  class="block mb-2 text-[13px] font-[700] text-[#515050] dark:text-white"
                  >Email</label
                >
                <input
                  v-model="user.email"
                  type="email"
                  name="price"
                  id="price"
                  class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-600 focus:border-blue-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                  placeholder="Email"
                  required=""
                />
              </div>
              <div>
                <label
                  for="category"
                  class="block mb-2 text-[13px] font-[700] text-[#515050] dark:text-white"
                  >Phone Number</label
                >
                <input v-model="user.phoneNumber" type="text" name="" id="" placeholder="Phone number" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-600 focus:border-blue-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
              </div>

              <div>
                <label
                  for="price"
                  class="block mb-2 text-[13px] font-[700] text-[#515050] dark:text-white"
                  >Occupation</label
                >
                <input
                  v-model="user.occupation"
                  type="text"
                  name="price"
                  id="price"
                  class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-600 focus:border-blue-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                  placeholder="Occupation"
                  required=""
                />
              </div>

              <div>
                <label
                  for="price"
                  class="block mb-2 text-sm font-medium text-gray-900 dark:text-white"
                  >Objective</label
                >
                <input
                  v-model="user.objective"
                  type="text"
                  name="price"
                  id="price"
                  class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-600 focus:border-blue-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                  placeholder="Objective"
                  required=""
                />
              </div>
            </div>
            <div class="w-[100%] h-0 border border-grey-300 mt-[47px] mb-[20px]"></div>
            <div class="w-[100%] flex justify-end">
                <button
                type="submit"
                class="text-white  inline-flex items-center bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
                >
                Save all
            </button>
        </div>
          </form>
        </div>
      </div>
    </div>

    <!------------------------ MODAL END ------------------------>


        <!-- Update user Modal -->
        <div
        tabindex="-1"
        aria-hidden="true"
        :class="
          updateModal
            ? 'overflow-y-auto bg-grey-200 flex overflow-x-hidden fixed top-0 right-0 left-0 z-50 justify-center items-center w-full md:inset-0 h-modal md:h-full'
            : 'hidden'
        "
      >
        <div class="relative p-4 w-full max-w-2xl h-full md:h-auto">
          <!-- Modal content -->
          <div class="relative p-4 bg-white rounded-lg shadow dark:bg-gray-800 sm:p-5">
            <!-- Modal header -->
            <div
              class="flex justify-between items-center pb-4 mb-4 rounded-t border-b sm:mb-5 dark:border-gray-600"
            >
              <h3 class="text-lg font-semibold text-gray-900 dark:text-white">
                Update user
              </h3>
              <button
                @click="toggleUpdateModal"
                type="button"
                class="text-gray-400 bg-transparent hover:bg-gray-200 hover:text-gray-900 rounded-lg text-sm p-1.5 ml-auto inline-flex items-center dark:hover:bg-gray-600 dark:hover:text-white"
              >
                <svg
                  aria-hidden="true"
                  class="w-5 h-5"
                  fill="currentColor"
                  viewBox="0 0 20 20"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    fill-rule="evenodd"
                    d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                    clip-rule="evenodd"
                  ></path>
                </svg>
                <span class="sr-only">Close modal</span>
              </button>
            </div>
            <!-- Modal body -->
            <form @submit.prevent="updateUser" class="w-[100%]">
              <div class="grid gap-4 mb-4 sm:grid-cols-2">
                <div>
                  <label
                    for="name"
                    class="block mb-2 text-[13px] font-[700] text-[#515050] dark:text-white"
                    >First Name</label
                  >
                  <input
                    v-model="user.firstName"
                    type="text"
                    name="name"
                    id="name"
                    class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-600 focus:border-blue-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                    :placeholder="user.firstName"
                    required=""
                  />
                </div>
  
                <div>
                  <label
                    for="brand"
                    class="block mb-2 text-[13px] font-[700] text-[#515050] dark:text-white"
                    >Last Name</label
                  >
                  <input
                    v-model="user.lastName"
                    type="text"
                    name="brand"
                    id="brand"
                    class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-600 focus:border-blue-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                    :placeholder="user.lastName"
                    required=""
                  />
                </div>
                <div>
                  <label
                    for="price"
                    class="block mb-2 text-[13px] font-[700] text-[#515050] dark:text-white"
                    >Email</label
                  >
                  <input
                    v-model="user.email"
                    type="email"
                    name="price"
                    id="price"
                    class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-600 focus:border-blue-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                    :placeholder="user.email"
                    required=""
                  />
                </div>
                <div>
                  <label
                    for="category"
                    class="block mb-2 text-[13px] font-[700] text-[#515050] dark:text-white"
                    >Phone Number</label
                  >
                  <input v-model="user.phoneNumber" type="text" name="" id="" :placeholder="user.phoneNumber" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-600 focus:border-blue-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
                </div>
  
                <div>
                  <label
                    for="price"
                    class="block mb-2 text-[13px] font-[700] text-[#515050] dark:text-white"
                    >Occupation</label
                  >
                  <input
                    v-model="user.occupation"
                    type="text"
                    name="price"
                    id="price"
                    class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-600 focus:border-blue-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                    :placeholder="user.occupation"
                    required=""
                  />
                </div>
  
                <div>
                  <label
                    for="price"
                    class="block mb-2 text-sm font-medium text-gray-900 dark:text-white"
                    >Objective</label
                  >
                  <input
                    v-model="user.objective"
                    type="text"
                    name="price"
                    id="price"
                    class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-600 focus:border-blue-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                    :placeholder="user.objective"
                    required=""
                  />
                </div>
              </div>
              <div class="w-[100%] h-0 border border-grey-300 mt-[47px] mb-[20px]"></div>
              <div class="w-[100%] flex justify-end">
                  <button
                  type="submit"
                  class="text-white  inline-flex items-center bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
                  >
                  Save all
              </button>
          </div>
            </form>
          </div>
        </div>
      </div>
  
      <!------------------------ MODAL END ------------------------>


 
  
    </template>
<script setup>


const updateModal = ref(false);
const toggleUpdateModal = () => {
        updateModal.value = !updateModal.value
        user.id= 0;
        user.firstName= '';
        user.lastName= '';
        user.phoneNumber= ''
        user.email= '';
        user.language= '';
        user.occupation= '';
        user.objective= '';
        user.subscription= '';
        user.image= '';
}
    

const Modal = ref(false);
const toggleModal = () => (Modal.value = !Modal.value);

const user = reactive({
        id: 1,
        firstName: '',
        lastName: '',
        phoneNumber: '',
        email: '',
        language: '',
        occupation: '',
        objective: '',
        subscription: '',
        image: ''
})

const updateModalFunc = (currentUser) => {
    toggleUpdateModal()
    user.id = currentUser.id
    user.firstName = currentUser.firstName;
    user.lastName = currentUser.lastName;
    user.phoneNumber = currentUser.phoneNumber;
    user.email = currentUser.email;
    user.occupation = currentUser.occupation;
    user.objective = currentUser.objective
}

const updateUser = () => {
    for(let el of NewUsers.value){
        if(el.id == user.id){
            el.firstName = user.firstName;
            el.lastName = user.lastName;
            el.phoneNumber = user.phoneNumber;
            el.email = user.email;
            el.occupation = user.occupation;
            el.objective = user.objective
        }
    }

        user.id= 0;
        user.firstName= '';
        user.lastName= '';
        user.phoneNumber= ''
        user.email= '';
        user.language= '';
        user.occupation= '';
        user.objective= '';
        user.subscription= '';
        user.image= '';

    toggleUpdateModal()
    
}

const deleteUser = (id) => {
    for(let i in NewUsers.value){
        if(NewUsers.value[i].id == id){
            NewUsers.value.splice(i,1)
            
        }
    }
    

}

const addUser = ()=> {
        user.id = Users.length+1;
        user.language = 'Russion';
        user.subscription = 'Mounthly';
        user.image = 'https://www.simplilearn.com/ice9/free_resources_article_thumb/what_is_image_Processing.jpg',
        NewUsers.value.push(user)
        toggleModal()
}

let pageItem=ref(5)
let page=ref(1)
let pages = ref(1)
let start = ref(1)
let finish = ref(0)
let paginated = ref([]) 

let NewUsers = ref([])

onMounted(() => { 
    NewUsers.value = Users
})


const list = computed(() => { 
    // console.log("Computed>>>>>", NewUsers.value.length);
    pages.value = NewUsers.value.length%pageItem.value ? Math.floor(NewUsers.value.length/pageItem.value)+1 : NewUsers.value.length/pageItem.value
    console.log('Pages.value>>>>', pages.value, page.value);
    if(pages.value<page.value && pages.value!=0){
        page.value = pages.value
    }
    start.value = page.value*pageItem.value-4;
    if(Users.length > start.value+pageItem.value-1){
    finish.value = start.value+pageItem.value-1
}else{
  finish.value = NewUsers.value.length
}
return NewUsers.value.slice(start.value-1, finish.value)
})

const add = () =>{
    if(page.value<pages.value){
        page.value = page.value+1
    }
    console.log(pages.value);
}

const minus = () => {
    if(page.value>1){
        page.value = page.value-1
    }
}



</script>
<style lang="">
    
</style>