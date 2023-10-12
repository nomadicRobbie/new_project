<template lang="">
  <div>
    <nav id="nav">
      <router-link to="/" class="navTag">Home</router-link>
      <router-link to="/about" class="navTag">About</router-link>
      <router-link to="/hireUs" class="navTag">Hire Us</router-link>
      <router-link to="/shop" class="navTag">Shop</router-link>
    </nav>
  </div>
  <transition mode="out-in" name="slide">
    <div class="nav-collapse" @click="navbarOpen = !navbarOpen">
      <p>=</p>
      <nav :class="navbarOpen ? 'show-nav' : 'hide-nav'">
        <router-link to="/" class="navTag">Home</router-link>
        <router-link to="/about" class="navTag">About</router-link>
        <router-link to="/hireUs" class="navTag">Hire Us</router-link>
        <router-link to="/shop" class="navTag">Shop</router-link>
      </nav>
    </div>
  </transition>
</template>
<script>
export default {
  name: "NavBar",
  data() {
    return {
      navbarOpen: false,
    };
  },
  methods: {
    beforeEnter(el) {
      el.style.transform = "translateX(100%)"; // Initial position for entering
    },
    enter(el, done) {
      el.style.transform = "translateX(0)"; // Final position for entering
      el.addEventListener("transitionend", () => console.log("enter Transition ended"), done);
    },
    beforeLeave(el) {
      el.style.transform = "translateX(0)"; // Initial position for leaving
    },
    leave(el, done) {
      el.style.transform = "translateX(-100%)"; // Final position for leaving
      el.addEventListener("transitionend", done);
      console.log(el);
    },
  },
};
</script>
<style scoped lang="scss">
.slide-enter-active,
.slide-leave-active {
  transition: transform 2000ms ease-in-out;
}
.slide-enter,
.slide-leave-to {
  transform: translateX(100%);
}
#nav {
  display: flex;
  padding: 1rem;
  justify-content: flex-end;
  .navTag {
    text-decoration: none;
    color: var(--action-colour);
    padding: 0rem 1rem;
  }
}

.nav-collapse {
  display: none;
}

#nav .active-link {
  font-weight: bold;
  border-bottom: 2px solid var(--action-colour);
}

@media only screen and (orientation: portrait) {
  #nav {
    display: none;
  }

  .hide-nav {
    display: none;
  }

  .nav-collapse {
    position: relative;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    height: 5rem;
    right: 0.5rem;
    top: 0rem;
    z-index: 10;

    p {
      font-size: xx-large;
      position: absolute;
      padding-right: 1rem;
    }
    .show-nav {
      position: relative;
      width: 80%;
      right: 2rem;
      top: 8rem;
      display: flex;
      flex-direction: column;
      background-color: var(--background-colour);
      box-shadow: 0px 5px 10px var(--action-colour);
      border-radius: 10px;

      .navTag {
        padding: 1rem;
        text-decoration: none;
        right: 5rem;
        color: var(--action-colour);
        font-size: large;
      }
    }
  }
}
</style>
