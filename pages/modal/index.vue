<template>
  <div class="min-vh-100 d-flex flex-column">
    <div class="flex-grow-1">
      <Header />
      <main>
        <b-container fluid="">
          <ModalAlert />
        </b-container>
      </main>
    </div>
    <Footer />
    <BottomNavigationMobile />
  </div>
</template>

<script>
  import Header from '@/components/shared/header';
  import Footer from '@/components/shared/footer';
  import ModalAlert from '@/components/modal/modal-alert';
  import BottomNavigationMobile from '@/components/shared/bottom-navigation-mobile';

  export default {
    components: {
      Header,
      Footer,
      BottomNavigationMobile,
      ModalAlert,
    }
  }
</script>
