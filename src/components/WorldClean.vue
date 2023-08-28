<template>
    <div class="world-clean wrapper">
        <div class="container">
            <div class="world-clean-header">
                <h3 class="title mb-4 text-center">We're committed to making the world cleaner</h3>
                <p class="text-dark-gray text-center mb-5">From development to operation, we create and operate valuable solar and storage <br> projects that benefit communities for decades.</p>

                <div class="progress-section">
                    <div class="row">
                        <div class="col-lg-3 col-md-6" v-for="item in items" :key="item">
                            <div class="progress-item">
                                <div class="circular-progress-bar">
                                    <Progress :percentage="item.text"/>
                                </div>
                                
                                <div class="progress-details text-center mt-3">
                                    <h5 class="title">{{ item.title }}</h5>
                                    <p class="text-dark-gray">{{ item.subtitle }}</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Progress from '@/components/progress/Progress.vue'

export default{
    name:'WorldClean',
    components:{
        Progress
    },
    data() {
        return {
            items:[
                {
                    text: 50,
                    title:'Geothermal',
                    subtitle:'We operate facilities across North America with 100+ wind sites in operation.'
                },
                {
                    text: 70,
                    title:'Bioenergy',
                    subtitle:'We operate facilities across North America with 100+ wind sites in operation.'
                },
                {
                    text: 80,
                    title:'Wind',
                    subtitle:'We operate facilities across North America with 100+ wind sites in operation.'
                },
                {
                    text: 70,
                    title:'Solar',
                    subtitle:'We operate facilities across North America with 100+ wind sites in operation.'
                },
            ],
        };
    },
    
}
</script>


<style>
.progress-item {
    padding: 0px 40px;
}
.circular-progress-bar {
    width: 180px;
    height: 180px;
    margin: 0 auto;
}
</style>
