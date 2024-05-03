<template>
  <header class="sticky-top">
    <nav class="navbar navbar-expand-lg">
      <div class="container">
        <a class="navbar-brand" href="#">
          <h1 class="fst-italic fw-bold fs-3 mb-0">Yuchen</h1>
        </a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNavAltMarkup"
          aria-controls="navbarNavAltMarkup"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
          <div class="navbar-nav ms-auto">
            <a class="nav-link active" aria-current="page" href="#">About</a>
            <a class="nav-link" href="#project-section">Project</a>
          </div>
        </div>
      </div>
    </nav>
  </header>
  <main>
    <section class="hero">
      <div class="banner container position-relative">
        <div
          class="position-absolute position-absolute top-50 start-50 translate-middle"
        >
          <h2 class="display-1">Hello</h2>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Officia
            quam necessitatibus omnis officiis architecto quod, odit quis
            corporis quidem pariatur dolorum, impedit reiciendis delectus nemo
            eligendi quos aperiam at mollitia molestiae aliquam. Placeat dolore
            quo dicta, accusamus, cupiditate nulla repellat repudiandae
            molestiae alias sunt aut culpa mollitia cum perspiciatis nostrum!
          </p>
        </div>
      </div>
    </section>
    <div class="container">
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Asperiores
        quisquam incidunt a beatae nobis, excepturi unde harum tenetur placeat
        ipsa mollitia enim ea explicabo ipsum nam expedita corrupti temporibus!
        Praesentium provident necessitatibus ea pariatur doloribus cum
        reprehenderit quibusdam cupiditate reiciendis, ratione odit nam repellat
        qui hic consequuntur magnam quam illum architecto molestias ipsum
        accusamus enim! Minus animi voluptatibus necessitatibus maiores autem
        commodi tempora amet cupiditate quisquam eveniet nesciunt optio libero
        dolor, deleniti perspiciatis quibusdam dicta aliquam, nulla nemo?
        Eligendi quasi molestias laboriosam aut iste, illo laborum tempore
        temporibus architecto dignissimos consequuntur? Debitis excepturi
        quaerat velit? Odit ea voluptatibus sed ex!
      </p>
    </div>
  </main>
  <footer class="fixed-bottom">
    <nav
      class="navbar"
      ref="footerNav"
      :class="{
        'bg-dark': isBottom,
        'bg-white': !isBottom,
        'link-light': isBottom,
        'link-dark': !isBottom,
        'bg-opacity-75': !isBottom,
      }"
      @scroll="handleScroll"
    >
      <div class="container">
        <div class="container-fluid d-flex justify-content-between">
          <a
            class="navbar-link d-flex align-items-center"
            :class="{ 'link-light': isBottom, 'link-dark': !isBottom }"
            href="#"
            >Contact<i class="fa-solid fa-square-arrow-up-right ms-1"></i
          ></a>
        </div>
      </div>
    </nav>
  </footer>
</template>

<script setup>
import { onMounted, onUnmounted, ref } from "vue";

const isBottom = ref(false);
const footerNav = ref(null);

const handleScroll = () => {
  if (window.innerHeight + window.scrollY >= document.body.offsetHeight) {
    // 滚动到底部，更改导航栏样式
    isBottom.value = true;
  } else {
    // 未滚动到底部，恢复默认样式
    isBottom.value = false;
  }
};

onMounted(() => {
  addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  addEventListener("scroll", handleScroll);
});
</script>

<style lang="scss" scoped>
.banner {
  height: calc(100vh - 4rem);
}
</style>
