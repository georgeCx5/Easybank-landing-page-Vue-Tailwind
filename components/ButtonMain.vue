<script>
export default {
   data() {
      return {

      }
   },
   props: {
      wSize: {
         String,
         required: true,
      }
   }
}
</script>
<template>
   <button
      :class="` ${wSize} h-[44px] bg-gradient-to-br from-neo-lime-green to-neo-bright-cyan text-neo-white text-[.875rem] leading-[1.75rem] font-bold rounded-[1.375rem]`">
      Request Invite
   </button>
</template>