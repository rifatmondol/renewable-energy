<template>
    <div class="project wrapper">
        <div class="project-main d-flex flex-start">
            <div class="project-item left w-50 position-relative">
                <!-- <img src="../assets/images/renewable6.jpg" alt="renewable6" class="w-100"> -->
                <div class="project-left-info info1 text-center">
                    <span class="d-inline-block">
                        <font-awesome-icon icon="fa-solid fa-info" />
                    </span>
                    <div class="info-details">
                        <h6>Solar Modules</h6>
                        <p class="mb-0 text-dark-gray">Produce electricity even on cloudy days, usually around 10%-20%.</p>
                    </div>
                </div>
                <div class="project-left-info info2 text-center">
                    <span class="d-inline-block">
                        <font-awesome-icon icon="fa-solid fa-info" />
                    </span>
                    <div class="info-details">
                        <h6>Low Maintenance</h6>
                        <p class="mb-0 text-dark-gray">This is because there are no moving parts in the solar system.</p>
                    </div>
                </div>
            </div>
            <div class="project-item right w-50">
                <p class="subtitle">EFFECTIVE SOLUTIONS FOR BETTER RESULTS</p>
                <h4>We have developed 200+ projects across country and continents</h4>
                <div class="project-inner">
                    <div class="row">
                        <div class="col-md-6 mt-5" v-for="item in items" :key="item">
                            <div class="project-inner-item">
                                <div class="project-inner-image mb-4">
                                    <img :src="item.src" :alt="item.src">
                                </div>
                                <div class="project-inner-text">
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
import icon8 from '@/assets/images/renewable-icon8.png'
import icon9 from '@/assets/images/renewable-icon9.png'
import icon10 from '@/assets/images/renewable-icon10.png'
import icon11 from '@/assets/images/renewable-icon11.png'
export default{
    name:'ProjectComponent',
    data(){
        return{
            items:[
                {
                    src:icon11,
                    title:'Environmental',
                    subtitle:"We are one of the nation’s leading providers of wholesale power generation services."
                },
                {
                    src:icon10,
                    title:'Management',
                    subtitle:"We are one of the nation’s leading providers of wholesale power generation services."
                },
                {
                    src:icon9,
                    title:'Resources',
                    subtitle:"We are one of the nation’s leading providers of wholesale power generation services."
                },
                {
                    src:icon8,
                    title:'Community',
                    subtitle:"We are one of the nation’s leading providers of wholesale power generation services."
                },
            ]
        }
    }
}
</script>