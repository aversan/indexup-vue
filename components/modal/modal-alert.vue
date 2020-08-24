<template>
  <b-modal visible size="md" modal-class="modal-alert" id="modal-alert" hide-footer header-bg-variant="danger" body-class="pt-2_5 px-3_75 pb-6 text-center" header-class="position-relative text-center bg-red-400" header-text-variant="white" centered>
    <template v-slot:modal-header="{ close }">
      <h5 class="h1 mb-0 flex-grow-1 modal-title">Вывод приостановлен!</h5>
      <svg class="modal-close clickable position-absolute" @click="close()" width="15" height="15" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M9.975 7.5l4.64 4.64a1.312 1.312 0 010 1.856l-.618.618a1.313 1.313 0 01-1.856 0L7.5 9.974 2.86 14.615a1.312 1.312 0 01-1.856 0l-.62-.618a1.313 1.313 0 010-1.856L5.027 7.5.386 2.859a1.313 1.313 0 010-1.856l.618-.619a1.313 1.313 0 011.856 0L7.5 5.025l4.64-4.64a1.313 1.313 0 011.857 0l.619.618a1.312 1.312 0 010 1.856L9.975 7.5z" fill="#C68D8B"/></svg>
    </template>
    <template v-slot:default="{ hide }">
      <p class="text-lg font-weight-medium mb-0 modal-text">
        Вывод доступен только пользоавтелям прошедшим верификацию, а также сделавшим ставку всего депозита с коэффициентом не ниже, чем 1.2 Подробности читайте  в разделе
        «<a class="text-primary" href="">Правила</a>»
      </p>
    </template>
  </b-modal>
</template>

<script>
  import '@/components/icons/close';

  export default {
  }
</script>

<style lang="scss">
  .modal-alert {
    .modal-header {
      height: 5.8125rem;
      overflow: hidden;

      &::before {
        content: '';
        width: 104px;
        height: 93px;
        position: absolute;
        left: 0;
        top: 0;
        bottom: 0;
        background-image: url("data:image/svg+xml,%3Csvg width='104' height='93' viewBox='0 0 104 93' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cg clip-path='url(%23clip0)'%3E%3Cpath d='M39.7451 11.5001C39.7451 14.4914 37.3432 16.9164 34.3804 16.9164C31.4175 16.9164 29.0156 14.4914 29.0156 11.5001C29.0156 8.50874 31.4175 6.08374 34.3804 6.08374C37.3432 6.08374 39.7451 8.50874 39.7451 11.5001Z' fill='%23901C18'/%3E%3Cpath d='M34.3806 81.9163C32.1595 81.9163 30.3568 80.0963 30.3568 77.8538V35.875H24.9921C22.7709 35.875 20.9683 34.055 20.9683 31.8125C20.9683 29.57 22.7709 27.75 24.9921 27.75H34.3806C36.6018 27.75 38.4044 29.57 38.4044 31.8125V77.8538C38.4044 80.0963 36.6018 81.9163 34.3806 81.9163Z' fill='%23901C18'/%3E%3Cpath d='M34.381 109C-1.12013 109 -30 79.8424 -30 44C-30 8.15756 -1.12013 -21 34.381 -21C69.882 -21 98.7619 8.15756 98.7619 44C98.7619 79.8424 69.882 109 34.381 109ZM34.381 -12.875C3.31726 -12.875 -21.9524 12.6376 -21.9524 44C-21.9524 75.3624 3.31726 100.875 34.381 100.875C65.4446 100.875 90.7143 75.3624 90.7143 44C90.7143 12.6376 65.4446 -12.875 34.381 -12.875Z' fill='%23901C18'/%3E%3Cpath d='M46.4523 81.9163H22.3095C20.0883 81.9163 18.2856 80.0963 18.2856 77.8538C18.2856 75.6113 20.0883 73.7913 22.3095 73.7913H46.4523C48.6735 73.7913 50.4761 75.6113 50.4761 77.8538C50.4761 80.0963 48.6735 81.9163 46.4523 81.9163Z' fill='%23901C18'/%3E%3C/g%3E%3Cdefs%3E%3CclipPath id='clip0'%3E%3Crect width='104' height='93' fill='white'/%3E%3C/clipPath%3E%3C/defs%3E%3C/svg%3E%0A");
      }
    }

    .modal-title {
      line-height: 2.875rem;
    }

    .modal-close {
      color: #C68D8B;
      top: .875rem;
      right: .875rem;

      &:hover {
        color: var(--white);
      }
    }

    .modal-text {
      line-height: 1.6666;
    }
  }
</style>
