<template>
    <div class="renewable wrapper">
        <div class="container">
            <h3 class="text-center title mb-3">Renewable energy is derived from natural processes</h3>
            <p class="text-center text-dark-gray mb-3 subtitle">We capture energy from existing flows of energy, from on-going natural processes, such as <br>
sunshine, wind, flowing water, biological processes, and geothermal heat flows.</p>
            <div class="renewable-main pt-5">
                <div class="row">
                    <div class="col-lg-3 col-md-6 mt-4 mb-4 col-sec" v-for="item in items" :key="item">
                        <div class="renewable-item">
                            <div class="number text-center mb-4 position-relative">
                                <span class="d-inline-block">{{ item.number }}</span>
                                <div class="hover"></div>
                            </div>
                            <div class="renewable-text">
                                <h5 class="title text-center mb-3">{{ item.title }}</h5>
                                <p class="text-dark-gray text-center mb-0">{{ item.subtitle }}</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
    </div>

</template>

<script>
export default{
    name:'RenewableComponent',
    data(){
        return{
            items:[
                {
                    number: '1',
                    title:'Resources',
                    subtitle:'We provide energy-related products and build energy infrastructure.'
                },
                {
                    number: '2',
                    title:'Manufacturing',
                    subtitle:'We provide energy-related products and build energy infrastructure.'
                },
                {
                    number: '3',
                    title:'Distribution',
                    subtitle:'We provide energy-related products and build energy infrastructure.'
                },
                {
                    number: '4',
                    title:'Demand',
                    subtitle:'We provide energy-related products and build energy infrastructure.'
                },
            ]
        }
    }
}
</script>