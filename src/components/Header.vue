<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <header class="position-fixed w-100 wrapper" :class="{ hovered: isHovered, sticky: isSticky }">
    <!-- Header top -->
    <div class="header-top">
      <div class="container">
        <div class="header-top-content d-flex justify-content-between">
          <div class="contact">
            <span><a href="tel:++12129462700">+1 212 946 2700</a></span>
            <span><router-link to="/">Help Desk</router-link></span>
            <span><router-link to="/">Why Sway</router-link></span>
          </div>
          <div class="social">
            <span
              ><a href="#"><font-awesome-icon icon="fa-brands fa-facebook-f" /></a
            ></span>
            <span
              ><a href="#"><font-awesome-icon icon="fa-brands fa-linkedin-in" /></a
            ></span>
            <span
              ><a href="#"><font-awesome-icon icon="fa-brands fa-twitter" /></a
            ></span>
          </div>
        </div>
      </div>
    </div>
    <!-- Main nav -->
    <nav class="navbar navbar-expand-lg py-0" :class="{ hovered: isHovered }">
      <div class="container">
        <router-link class="navbar-brand" to="/">SWAY </router-link>
        <ul class="navbar-nav justify-content-end flex-row flex-grow-1">
            <li class="nav-item search position-relative d-block d-lg-none">
                <router-link to="/" class="nav-link py-0" @click="searchClick()">
                    <font-awesome-icon icon="fa-solid fa-magnifying-glass" v-if="IsActive == false"/>
                    <font-awesome-icon icon="fa-solid fa-xmark" v-else @click.stop.prevent="closeClick()"/>
                </router-link>
                <!-- Search Box -->
                <div
                    class="input-box position-absolute"
                    :class="{ active: IsActive }"
                >
                    <input type="text" class="border w-100 h-50 p-2" placeholder="Search..." />
                    <span class="close ms-2">
                        <font-awesome-icon icon="fa-solid fa-magnifying-glass" />
                    </span>
                </div>
                <!-- Search Box -->
            </li>
            
        </ul>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="offcanvas"
          data-bs-target="#offcanvasNavbar"
          aria-controls="offcanvasNavbar"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div
          class="offcanvas offcanvas-end"
          tabindex="-1"
          id="offcanvasNavbar"
          aria-labelledby="offcanvasNavbarLabel"
        >
          <div class="offcanvas-header">
            <router-link class="navbar-brand" to="/">SWAY</router-link>
            <button
              type="button"
              class="btn-close"
              data-bs-dismiss="offcanvas"
              aria-label="Close"
            ></button>
          </div>
          <div class="offcanvas-body">
            <ul class="navbar-nav justify-content-end flex-grow-1 main-nav">
              <li class="nav-item" 
              v-for="(menu, index) in megamenus" 
              :key="index"
              @mouseover="menu.dropdown ? setHovered(true) : '' "
              @mouseout="setHovered(false)"
              >
                <router-link
                  class="nav-link"
                  :class="{ 'dropdown-toggle': menu.dropdown }"
                  :to="menu.url"
                  >{{ menu.text }}
                </router-link>
                <div
                  class="mega-menu w-100 py-lg-5 position-absolute d-none"
                  :class="{ active: menu.dropdown }"
                >
                  <div class="row">
                    <div class="mega-main mb-lg-0 mb-2 col-lg" v-for="(submenu, subindex) in menu.subnav" :key="subindex" >
                      <ul class="dropdown-menu pt-0">
                        <li v-for="(item, itemindex) in submenu" :key="itemindex">
                          <router-link class="dropdown-item" :to="item.url">{{
                            item.text
                          }}</router-link>
                        </li>
                      </ul>
                    </div>
                  </div>
                </div>
              </li>

              <li class="nav-item flag-item position-relative">
                <router-link class="nav-link dropdown-toggle d-block" to="/" @click.prevent="showubmenu">
                  <img src="@/assets/images/en-flag.png" alt="flag"/>
                  <span class="d-md-none ms-2">English</span>
                </router-link>
                <ul class="flag position-absolute" :class="{active: isClicked}">
                  <li v-for="flag in flags" :key="flag.value">
                    <router-link to="/" class="d-block pb-1">
                      <img :src="flag.value" :alt="flag.value" />
                      <span class="d-inline-block ms-2">{{ flag.name }}</span
                      ></router-link
                    >
                  </li>
                </ul>
              </li>
              
              <li class="nav-item search position-relative d-none d-lg-block">
                <router-link to="/" @click="searchClick()">
                  <font-awesome-icon icon="fa-solid fa-magnifying-glass" v-if="IsActive == false"/>
                  <font-awesome-icon icon="fa-solid fa-xmark" v-else @click.stop.prevent="closeClick()"/>
                </router-link>
                <!-- Search Box -->
                <div
                  class="input-box position-absolute"
                  :class="{ active: IsActive }"
                >
                  <input type="text" class="border-0 w-100 h-50 p-2" placeholder="Search..." />
                  <span class="close ms-2">
                    <font-awesome-icon icon="fa-solid fa-magnifying-glass" />
                  </span>
                </div>
                <!-- Search Box -->
              </li>
              <li class="nav-item contact-btn">
                <router-link to="/" class="nav-link text-center bg-light-green">Contact Us</router-link>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
// import {en} from "@/lang/en";
import enFlag from '@/assets/images/en-flag.png'
import frFlag from '@/assets/images/fr-flag.png'
import deFlag from '@/assets/images/de-flag.png'

export default {
  name: 'HeaderComponent',
  data() {
    return {
      IsActive: false,
      isHovered: false,
      isSticky: false,
      isClicked: false,
      megamenus: [
        { text: 'Home', url: '/' },
        { text: 'About', url: '/' },
        {
          text: 'Portfolio',
          url: '/',
          dropdown: true,
          subnav: [
            [
              { text: 'Portfolio 1', url: '/' },
              { text: 'Portfolio 2', url: '/' },
              { text: 'Portfolio 3', url: '/' },
              { text: 'Portfolio 4', url: '/' },
              { text: 'Portfolio 5', url: '/' }
            ],
            [
              { text: 'Portfolio 1', url: '/' },
              { text: 'Portfolio 2', url: '/' },
              { text: 'Portfolio 3', url: '/' },
              { text: 'Portfolio 4', url: '/' },
              { text: 'Portfolio 5', url: '/' }
            ],
            [
              { text: 'Portfolio 1', url: '/' },
              { text: 'Portfolio 2', url: '/' },
              { text: 'Portfolio 3', url: '/' },
              { text: 'Portfolio 4', url: '/' },
              { text: 'Portfolio 5', url: '/' }
            ],
            [
              { text: 'Portfolio 1', url: '/' },
              { text: 'Portfolio 2', url: '/' },
              { text: 'Portfolio 3', url: '/' },
              { text: 'Portfolio 4', url: '/' },
              { text: 'Portfolio 5', url: '/' }
            ],
            [
              { text: 'Portfolio 1', url: '/' },
              { text: 'Portfolio 2', url: '/' },
              { text: 'Portfolio 3', url: '/' },
              { text: 'Portfolio 4', url: '/' },
              { text: 'Portfolio 5', url: '/' }
            ],
            [
              { text: 'Portfolio 1', url: '/' },
              { text: 'Portfolio 2', url: '/' },
              { text: 'Portfolio 3', url: '/' },
              { text: 'Portfolio 4', url: '/' },
              { text: 'Portfolio 5', url: '/' }
            ],
            
          ],
        },
        {
          text: 'Blog',
          url: '/',
          dropdown: true,
          subnav: [
            [
              { text: 'Classic', url: '/' },
              { text: 'Classic sidebar', url: '/' },
              { text: 'Left image list', url: '/' },
              { text: 'Left image sidebar', url: '/' },
              { text: 'Minimal list', url: '/' },
              { text: 'Minimal list sidebar', url: '/' },
            ],
            [
              { text: 'Detailed grid', url: '/' },
              { text: 'Detailed grid sidebar', url: '/' },
              { text: 'Minimal grid', url: '/' },
              { text: 'Minimal grid sidebar', url: '/' },
            ],
            [
              { text: 'Classic', url: '/' },
              { text: 'Classic sidebar', url: '/' },
              { text: 'Modern', url: '/' },
              { text: 'Modern sidebar', url: '/' },
            ],
            [
              { text: 'Standard post', url: '/' },
              { text: 'Video post', url: '/' },
              { text: 'Gallery post', url: '/' },
              { text: 'Audio post', url: '/' },
            ],
          ],
          
        },
        {
          text: 'Shop',
          url: '/',
          dropdown: true,
          subnav: [
            [
              { text: 'Shop 1', url: '/' },
              { text: 'Shop 2', url: '/' },
              { text: 'Shop 3', url: '/' },
              { text: 'Shop 4', url: '/' },
              { text: 'Shop 5', url: '/' }
            ],
            [
              { text: 'Shop 1', url: '/' },
              { text: 'Shop 2', url: '/' },
              { text: 'Shop 3', url: '/' },
              { text: 'Shop 4', url: '/' },
              { text: 'Shop 5', url: '/' }
            ],
            [
              { text: 'Shop 1', url: '/' },
              { text: 'Shop 2', url: '/' },
              { text: 'Shop 3', url: '/' },
              { text: 'Shop 4', url: '/' },
              { text: 'Shop 5', url: '/' }
            ],
            [
              { text: 'Shop 1', url: '/' },
              { text: 'Shop 2', url: '/' },
              { text: 'Shop 3', url: '/' },
              { text: 'Shop 4', url: '/' },
              { text: 'Shop 5', url: '/' }
            ],
            [
              { text: 'Shop 1', url: '/' },
              { text: 'Shop 2', url: '/' },
              { text: 'Shop 3', url: '/' },
              { text: 'Shop 4', url: '/' },
              { text: 'Shop 5', url: '/' }
            ],
          ],
         
        },
        { text: 'Blocks', url: '/' },
        { text: 'Elements', url: '/' },
        { text: 'Extra', url: '/' }
      ],
      flags: [
        { value: enFlag, name: 'English' },
        { value: frFlag, name: 'Francais' },
        { value: deFlag, name: 'Deutsch' }
      ]
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeUnmounted() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    searchClick() {
      this.IsActive = true
    },
    closeClick() {
      this.IsActive = false
    },
    setHovered(value) {
      this.isHovered = value  
    },
    showubmenu(){
      this.isClicked = !this.isClicked;
    },
    handleScroll(){
      if (window.scrollY > 150) {
        this.isSticky = true;
      } else {
        this.isSticky = false;
      }
    },
    // computedClass(menu){
    //   if(menu.subnav.length > 4){
    //     return 'col-lg'
    //   }
    //   else if(menu.subnav.length == 3){
    //     return 'col-lg-4'
    //   }
    //   else if(menu.subnav.length <= 4){
    //     return 'col-lg-3'
    //   }
      
    // }
  },
  computed:{
    // computedClass(){
    //   return{
    //     'col-lg-2': this.megamenus.filter( menu => menu.subnav.length > 4), 
    //     'col-lg-3': this.megamenus.filter( menu => menu.subnav.length <= 4),
    //     'col-lg-4': this.megamenus.filter( menu => menu.subnav.length == 3)
    //   }
    // }
  }

  // beforeMount() {
  //     localStorage.setItem("language", JSON.stringify(en));
  //     this.getLang = JSON.parse(localStorage.getItem("language") || '[]');
  // },
}
</script>

<style>


</style>