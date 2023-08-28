<template>
    <div class="project responsibility wrapper">
        <div class="project-main responsibility-main d-flex flex-start">
            <div class="project-item responsibility-item left w-50 position-relative order-2">
                <!-- <img src="../assets/images/renewable7.jpg" alt="renewable6" class="w-100"> -->
                <div class="project-left-info responsibility-left-info info1 text-center">
                    <span class="d-inline-block">
                        <font-awesome-icon icon="fa-solid fa-info" />
                    </span>
                    <div class="info-details">
                        <h6>Wind Energy</h6>
                        <p class="mb-0 text-dark-gray">Wind is used to generate mechanical power or electricity</p>
                    </div>
                </div>
                <div class="project-left-info responsibility-left-info info2 text-center">
                    <span class="d-inline-block">
                        <font-awesome-icon icon="fa-solid fa-info" />
                    </span>
                    <div class="info-details">
                        <h6>Vertical-Axis Turbines</h6>
                        <p class="mb-0 text-dark-gray">Wind turbines can be built on land or offshore in water.</p>
                    </div>
                </div>
                <div class="project-left-info responsibility-left-info info3 text-center">
                    <span class="d-inline-block">
                        <font-awesome-icon icon="fa-solid fa-info" />
                    </span>
                    <div class="info-details">
                        <h6>Land Turbines</h6>
                        <p class="mb-0 text-dark-gray">Land-based wind turbines range in size from 100 kilowatts</p>
                    </div>
                </div>
            </div>
            <div class="project-item responsibility-item right w-50">
                <p class="subtitle">WE'RE CREATING A BETTER ENERGY FUTURE</p>
                <h4>We believe in acting responsibly & sustainably in our operations</h4>
                <div class="project-inner responsibility-inner">
                    <div class="row">
                        <div class="col-md-12 mt-5" v-for="item in items" :key="item">
                            <div class="project-inner-item responsibility-inner-item d-flex">
                                <div class="project-inner-image responsibility-inner-image mb-4 me-md-4">
                                    <img :src="item.src" :alt="item.src">
                                </div>
                                <div class="project-inner-text responsibility-inner-text">
                                    <h5 class="mb-3">{{ item.title }}</h5>
                                    <p class="mb-0 text-dark-gray-2 pe-3">{{ item.subtitle }}</p>
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
import icon5 from '@/assets/images/renewable-icon5.png'
import icon6 from '@/assets/images/renewable-icon6.png'
import icon7 from '@/assets/images/renewable-icon7.png'

export default{
    name:'ProjectComponent',
    data(){
        return{
            items:[
                {
                    src:icon5,
                    title:'Custom Energy Solutions',
                    subtitle:'Our investment totals more than $20 billion in clean and renewable technologies.'
                },
                {
                    src:icon6,
                    title:'Asset Management Services',
                    subtitle:'Our investment totals more than $20 billion in clean and renewable technologies.'
                },
                {
                    src:icon7,
                    title:'Operations & Maintenance',
                    subtitle:'Our investment totals more than $20 billion in clean and renewable technologies.'
                },
                
            ]
        }
    }
}
</script>


<style>

</style>