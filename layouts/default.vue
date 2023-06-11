<template>
    <div>
    <main>
        <div class="flex reletive">
            <aside class="h-[100vh] fixed border ">
                <Sidebar/>
            </aside>
           <div class="ml-[245px] w-[90%] bg-[#F5F5F9]">


                <Header/>

                <div class="px-[61px]">
                    <slot/>
                </div>
            
            </div>
           
        </div>
        
    </main>
        <!-- Footer -->
    </div>
</template>

<script setup>

</script>

<style scoped>

</style>