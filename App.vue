<script>
import FooterLogo from './components/FooterLogo.vue'

import logo from '@/assets/images/logo.svg?url'
import iconClose from '@/assets/images/icon-close.svg?url'
import iconHamburger from '@/assets/images/icon-hamburger.svg?url'
import imgHeader from '@/assets/images/image-mockups.png'

import iconOnline from '@/assets/images/icon-online.svg?url'
import iconBudgeting from '@/assets/images/icon-budgeting.svg?url'
import iconOnboarding from '@/assets/images/icon-onboarding.svg?url'
import iconApi from '@/assets/images/icon-api.svg?url'

import imgConfetti from '@/assets/images/image-confetti.jpg'
import imgCurrency from '@/assets/images/image-currency.jpg'
import imgPlane from '@/assets/images/image-plane.jpg'
import imgRestaurant from '@/assets/images/image-restaurant.jpg'
import ButtonMain from './components/ButtonMain.vue'

export default {
  data() {
    return {
      logo,
      iconClose,
      iconHamburger,
      isNavOpen: false,
      bgMB: 'bg-[url(@/assets/images/bg-intro-mobile.svg?url)]',
      bgDT: 'bg-[url(@/assets/images/bg-intro-desktop.svg?url)]',
      imgHeader,
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
          image: imgCurrency,
          autor: 'Claire Robinson',
          header: 'Receive money in any currency with no fees',
          main: 'The world is getting smaller and we’re becoming more mobile. So why should you be forced to only receive money in a single …',
        },
        {
          image: imgRestaurant,
          autor: 'Wilson Hutton',
          header: 'Treat yourself without worrying about money',
          main: 'Our simple budgeting feature allows you to separate out your spending and set realistic limits each month. That means you …',
        },
        {
          image: imgPlane,
          autor: 'Wilson Hutton',
          header: 'Take your Easybank card wherever you go',
          main: 'We want you to enjoy your travels. This is why we don’t charge any fees on purchases while you’re abroad. We’ll even show you …',
        },
        {
          image: imgConfetti,
          autor: 'By Claire Robinson',
          header: 'Our invite-only Beta accounts are now live!',
          main: 'After a lot of hard work by the whole team, we’re excited to launch our closed beta. It’s easy to request an invite through the site ...',
        },
      ]
    };
  },
  components: { FooterLogo, ButtonMain }
}
</script>
<template>
  <body class=" flex flex-col items-center text-neo-dark-blue font-public">
    <header class=" w-full max-w-[425px]">
      <nav class=" fixed flex justify-between items-center w-full max-w-[425px] px-6 py-5 bg-neo-white">
        <img :src="logo" alt="logo">
        <button>
          <img v-show="isNavOpen == false" :src="iconHamburger" alt="iconHamburger">
          <img v-show="isNavOpen == true" :src="iconClose" alt="iconClose">
        </button>
      </nav>
      <img :src="imgHeader" alt="">
      <div class=" flex flex-col items-center text-center">
        <h1 class=" text-[2.5rem] leading-[3rem] tracking-[-.05rem] font-light">
          Next generation digital banking</h1>
        <p class=" text-neo-grayish-blue text-[1rem] leading-[1.5rem] tracking-[-.015rem]">
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
            <img class=" mb-6 select-none" :src="item.icon" :alt="`Icon ${index + 1}`">
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
            <img class=" rounded-t-[.3125rem] select-none" :src="item.image" alt="" draggable="false">
            <div class=" flex flex-col gap-2 px-8 py-6 bg-neo-white">
              <h6 class=" text-neo-grayish-blue text-[.625rem] leading-[1.125rem] tracking-[-.01rem]">
                By {{ item.autor }}</h6>
              <h4 class=" text-[1rem] leading-[1.25rem] tracking-[-.02rem] font-light">
                {{ item.header }}</h4>
              <p class=" text-neo-grayish-blue text-[.8125rem] leading-[1.125rem] tracking-[-.0125rem]">
                {{ item.main }}
              </p>
            </div>
          </article>
        </div>
      </section>
    </main>
    <footer
      class=" w-full max-w-[425px] bg-neo-dark-blue text-neo-white text-[.9375rem] leading-[1.625rem] tracking-[-.015rem]">
      <FooterLogo />
      <ul class=" flex flex-col">
        <li>About Us</li>
        <li>Contact</li>
        <li>Blog</li>
      </ul>
      <ul class=" flex flex-col">
        <li>Careers</li>
        <li>Support</li>
        <li>Privacy Policy</li>
      </ul>
      <ButtonMain w-size="w-[163px]" />
      <p class=" text-neo-white text-opacity-50">
        © Easybank. All Rights Reserved
      </p>
    </footer>
  </body>
</template>