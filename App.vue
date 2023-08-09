<script>
import ButtonMain from '@/components/ButtonMain.vue'
import FooterLogo from '@/components/FooterLogo.vue'
import FooterNetwork from '@/components/FooterNetwork.vue'

import logo from '@/assets/images/logo.svg?url'
import iconClose from '@/assets/images/icon-close.svg?url'
import iconHamburger from '@/assets/images/icon-hamburger.svg?url'
import imgHeader from '@/assets/images/image-mockups.png'

import iconOnline from '@/assets/images/icon-online.svg?url'
import iconBudgeting from '@/assets/images/icon-budgeting.svg?url'
import iconOnboarding from '@/assets/images/icon-onboarding.svg?url'
import iconApi from '@/assets/images/icon-api.svg?url'


export default {
  data() {
    return {
      logo,
      iconClose,
      iconHamburger,
      isNavOpen: false,
      bgMB: 'bg-[url(@/assets/images/bg-intro-mobile.svg?url)]',
      bgDT: 'DT:bg-[url(@/assets/images/bg-intro-desktop.svg?url)]',
      imgHeader,
      dataNav: [
        'Home',
        'About',
        'Contact',
        'Blog',
        'Careers',
      ],
      dataOne: [
        {
          icon: iconOnline,
          header: 'Online Banking',
          main: 'Our modern web and mobile applications allow you to keep track of your finances wherever you are in the world.',
        },
        {
          icon: iconBudgeting,
          header: 'Simple Budgeting',
          main: 'See exactly where your money goes each month. Receive notifications when you’re close to hitting your limits.',
        },
        {
          icon: iconOnboarding,
          header: 'Fast Onboarding',
          main: 'We don’t do branches. Open your account in minutes online and start taking control of your finances right away.',
        },
        {
          icon: iconApi,
          header: 'Open API',
          main: 'Manage your savings, investments, pension, and much more from one account. Tracking your money has never been easier.',
        },
      ],
      dataTwo: [
        {
          image: 'bg-[url(@/assets/images/image-currency.jpg)]',
          autor: 'Claire Robinson',
          header: 'Receive money in any currency with no fees',
          main: 'The world is getting smaller and we’re becoming more mobile. So why should you be forced to only receive money in a single …',
        },
        {
          image: 'bg-[url(@/assets/images/image-restaurant.jpg)]',
          autor: 'Wilson Hutton',
          header: 'Treat yourself without worrying about money',
          main: 'Our simple budgeting feature allows you to separate out your spending and set realistic limits each month. That means you …',
        },
        {
          image: 'bg-[url(@/assets/images/image-plane.jpg)]',
          autor: 'Wilson Hutton',
          header: 'Take your Easybank card wherever you go',
          main: 'We want you to enjoy your travels. This is why we don’t charge any fees on purchases while you’re abroad. We’ll even show you …',
        },
        {
          image: 'bg-[url(@/assets/images/image-confetti.jpg)]',
          autor: 'By Claire Robinson',
          header: 'Our invite-only Beta accounts are now live!',
          main: 'After a lot of hard work by the whole team, we’re excited to launch our closed beta. It’s easy to request an invite through the site ...',
        },
      ],
      dataFooter: [
        'About Us',
        'Contact',
        'Blog',
        'Careers',
        'Support',
        'Privacy Policy',
      ]
    };
  },
  components: {
    FooterLogo,
    ButtonMain,
    FooterNetwork
  }
}
</script>
<template>
  <body class=" flex flex-col items-center text-neo-dark-blue font-public">
    <header class=" relative w-full max-w-[425px] pb-[5.5rem]">
      <div :class="` absolute top-0 left-0 w-full h-[398px] ${bgMB} bg-no-repeat z-0`"></div>
      <nav class=" fixed flex justify-between items-center w-full max-w-[425px] px-6 py-5 bg-neo-white select-none z-40">
        <img :src="logo" alt="logo" draggable="false">
        <button @click="isNavOpen = !isNavOpen">
          <img v-show="isNavOpen == false" :src="iconHamburger" alt="iconHamburger" draggable="false">
          <img v-show="isNavOpen == true" :src="iconClose" alt="iconClose" draggable="false">
        </button>
        <div v-show="isNavOpen" class=" absolute top-[3.75rem] left-0 w-full">
          <!-- Shadow Layer -->
          <div class=" absolute w-full h-[603px] bg-gradient-to-b from-neo-dark-blue to-transparent"></div>
          <!-- Nav Buttons -->
          <div class=" relative flex flex-col items-center gap-6 mx-6 mt-6 py-8 bg-neo-white rounded z-10">
            <button v-for="item in dataNav"
              class=" hover:text-neo-lime-green text-[1.125rem] leading-[1.3125rem] tracking-[-.00875rem]">
              {{ item }}
            </button>
          </div>
        </div>
      </nav>
      <img class=" relative top-[-4rem] px-3 z-20 select-none" :src="imgHeader" alt="imgHeader" draggable="false">
      <div class=" flex flex-col items-center text-center -mt-10">
        <h1 class=" mb-4 text-[2.5rem] leading-[3rem] tracking-[-.05rem] font-light">
          Next generation digital banking</h1>
        <p class=" mb-8 text-neo-grayish-blue text-[1rem] leading-[1.5rem] tracking-[-.015rem]">
          Take your financial life online. Your Easybank account will be a one-stop-shop
          for spending, saving, budgeting, investing, and much more.
        </p>
        <ButtonMain w-size="w-[166px]" />
      </div>
    </header>
    <main class=" w-full max-w-[425px]">
      <section class=" flex flex-col gap-14 px-6 py-16 bg-neo-light-grayish-blue">
        <div class=" flex flex-col gap-[.875rem] text-center">
          <h2 class=" text-[2rem] leading-[2.375rem] tracking-[-.035rem] font-light">
            Why choose Easybank?</h2>
          <p class=" text-neo-grayish-blue text-[1rem] leading-[1.5rem] tracking-[-.015rem]">
            We leverage Open Banking to turn your bank account into your financial hub. Control
            your finances like never before.
          </p>
        </div>
        <div class=" flex flex-col gap-8">
          <article v-for="(item, index) in dataOne" class=" flex flex-col items-center text-center">
            <img class=" mb-6 select-none" :src="item.icon" :alt="`Icon ${index + 1}`" draggable="false">
            <h4 class=" mb-4 text-[1.25rem] leading-[1.75rem] tracking-[-.0225rem] font-light">
              {{ item.header }}</h4>
            <p class=" text-neo-grayish-blue text-[.9375rem] leading-[1.625rem] tracking-[-.015rem]">
              {{ item.main }}
            </p>
          </article>
        </div>
      </section>
      <section class=" flex flex-col gap-8 px-6 py-[5.5rem] bg-neo-very-light-gray">
        <h2 class=" text-[2rem] leading-[2.375rem] tracking-[-.035rem] font-light text-center">
          Latest Articles</h2>
        <div class=" flex flex-col gap-6">
          <article v-for="item in dataTwo">
            <div :class="`w-full h-[200px] ${item.image} bg-cover bg-center rounded-t-[.3125rem] select-none`"></div>
            <div class=" flex flex-col gap-2 px-8 py-6 bg-neo-white">
              <h6 class=" text-neo-grayish-blue text-[.625rem] leading-[1.125rem] tracking-[-.01rem]">
                By {{ item.autor }}</h6>
              <h4 class=" text-[1rem] leading-[1.25rem] tracking-[-.02rem] font-light">
                {{ item.header }}</h4>
              <p class=" pb-4 text-neo-grayish-blue text-[.8125rem] leading-[1.125rem] tracking-[-.0125rem]">
                {{ item.main }}
              </p>
            </div>
          </article>
        </div>
      </section>
    </main>
    <footer
      class=" flex flex-col gap-8 w-full max-w-[425px] py-10 bg-neo-dark-blue text-neo-white text-center text-[.9375rem] leading-[1.625rem] tracking-[-.015rem]">
      <div class=" flex flex-col items-center gap-8 select-none">
        <FooterLogo />
        <div class=" flex items-center gap-4">
          <FooterNetwork v-for="number in 5" :data-index="number - 1" />
        </div>
      </div>
      <div class=" flex flex-col items-center gap-2 select-none">
        <ul class=" flex flex-col gap-2">
          <li v-for="item in 3" class=" hover:text-neo-lime-green cursor-pointer">
            {{ dataFooter[item - 1] }}</li>
        </ul>
        <ul class=" flex flex-col gap-2">
          <li v-for="item in 3" class=" hover:text-neo-lime-green cursor-pointer">
            {{ dataFooter[item + 2] }}</li>
        </ul>
      </div>
      <div class=" flex flex-col items-center gap-6 ">
        <ButtonMain w-size="w-[163px]" />
        <p class=" text-neo-white text-opacity-50">
          © Easybank. All Rights Reserved
        </p>
      </div>
    </footer>
  </body>
</template>