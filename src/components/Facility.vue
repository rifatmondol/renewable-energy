<template>
    <div class="facility wrapper">
        <div class="container">
            <div class="facility-main">
                <div class="facility-header">
                    <p class="subtitle text-center">POWERING A SUSTAINABLE FUTURE, ONE PROJECT AT A TIME</p>
                    <h2 class="title text-center">We have designed many renewable energy <br> facilities across multiple countries</h2>
                </div>
                <div class="facility-part mt-5">
                    <div class="row">
                        <div class="col-lg-5">
                            <div class="facility-item left">
                                <h4 class="title mb-4">
                                    We're building a better <br> energy future for all
                                </h4>
                                <p class="text-gray-blue mb-5">Sway is committed to making the world cleaner and healthier. From development to operation, we create and operate valuable solar and storage projects that benefit communities for decades.</p>
                                <router-link to="/" class="d-inline-block text-decoration-none bg-light-green position-relative">Our Services 
                                    <span class="ms-1 d-inline-block">
                                        <font-awesome-icon icon="fa-solid fa-angle-right" />
                                    </span>
                                </router-link>
                            </div>
                        </div>
                        <div class="col-lg-7">
                            <div class="facility-item right d-flex position-relative">
                                <div class="facility-image-box box-1 ms-5 position-absolute">
                                    <img src="../assets/images/renewable4.jpg" alt="renewable4" class="w-100 ms-5">
                                </div>
                                <div class="facility-image-box box-2 position-absolute">
                                    <img src="../assets/images/renewable5.jpg" alt="renewable4" class="w-100">
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
export default{
    name: "FacilityComponent",
    data(){
        return{

        }
    }
}
</script>