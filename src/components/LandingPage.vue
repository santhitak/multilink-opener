<template>
  <section class="h-screen">
    <div class="h-100 w-100 d-flex justify-center align-center">
      <div class="d-flex justify-space-between w-75 align-center h-75">
        <div class="w-75">
          <p class="text-h2 text-center font-weight-bold">MULTILINK</p>
          <p class="text-h2 text-center font-weight-bold">OPENER</p>
          <p class="text-p text-center mt-4">
            Much faster way to open all the links you got
          </p>
        </div>
        <v-divider class="h-100" vertical></v-divider>
        <div class="w-50 d-flex align-center flex-column mx-10">
          <v-btn color="black" class="w-100 my-2" @click="scroll('usage')">
            use now
          </v-btn>
          <v-btn class="w-100 my-2" variant="outlined" @click="scroll('howto')">
            how to use ?
          </v-btn>
          <v-btn
            icon
            color="white"
            class="mt-4"
            href="https://github.com/santhitak/multilink-opener"
            target="_blank"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="24"
              height="24"
              viewBox="0 0 24 24"
            >
              <path
                d="M12 0c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm2.218 18.616c-.354.069-.468-.149-.468-.336v-1.921c0-.653-.229-1.079-.481-1.296 1.56-.173 3.198-.765 3.198-3.454 0-.765-.273-1.389-.721-1.879.072-.177.312-.889-.069-1.853 0 0-.587-.188-1.923.717-.561-.154-1.159-.231-1.754-.234-.595.003-1.193.08-1.753.235-1.337-.905-1.925-.717-1.925-.717-.379.964-.14 1.676-.067 1.852-.448.49-.722 1.114-.722 1.879 0 2.682 1.634 3.282 3.189 3.459-.2.175-.381.483-.444.936-.4.179-1.413.488-2.037-.582 0 0-.37-.672-1.073-.722 0 0-.683-.009-.048.426 0 0 .46.215.777 1.024 0 0 .405 1.25 2.353.826v1.303c0 .185-.113.402-.462.337-2.782-.925-4.788-3.549-4.788-6.641 0-3.867 3.135-7 7-7s7 3.133 7 7c0 3.091-2.003 5.715-4.782 6.641z"
              />
            </svg>
          </v-btn>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  methods: {
    scroll(id) {
      document.getElementById(id).scrollIntoView({
        behavior: "smooth",
      });
    },
  },
};
</script>
