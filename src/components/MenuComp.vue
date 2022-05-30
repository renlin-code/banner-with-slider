<template>
  <nav
    :class="[show ? 'main-container--open' : 'main-container--closed']"
    class="main-container"
  >
    <ul class="main-container__menu-list">
      <li class="menu-list__item"><a href="/">Главная</a></li>
      <li class="menu-list__item"><a href="/about">О компании</a></li>
      <li class="menu-list__item"><a href="/services">Услуги</a></li>
      <li class="menu-list__item"><a href="/news">Новости</a></li>
      <li class="menu-list__item"><a href="/career">Карьера</a></li>
      <li class="menu-list__item"><a href="/contacts">Контакты</a></li>
    </ul>
    <ul class="main-container__contacts-list">
      <li class="contacts-list__item">
        <a href="#"
          ><span class="icon telephone-icon"></span
          ><span class="text">+7(000) 000 00-00</span></a
        >
      </li>
      <li class="icon contacts-list__item">
        <a href="#"
          ><span class="icon mail-icon"></span
          ><span class="text">example@mail.ru</span></a
        >
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  props: {
    show: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style scoped>
.main-container {
  position: absolute;
  top: 70px;
  left: -100vw;
  width: 100vw;
  height: calc(100vh - 70px);
  padding: 0 var(--general-padding);
  background-color: var(--white);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  transition: all 500ms ease;
  z-index: 1;
}
.main-container ul {
  list-style: none;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
}

.main-container ul li a {
  text-decoration: none;
  font-weight: bold;
}
.main-container .main-container__menu-list {
  margin-bottom: 20vh;
  gap: 30px;
}
.main-container .main-container__menu-list .menu-list__item a {
  font-size: 2.3rem;
  line-height: 2.5rem;
  color: var(--black);
}
.main-container .main-container__menu-list .menu-list__item a:hover {
  color: var(--dark-blue);
  border-bottom: 1.5px solid var(--dark-blue);
}
.main-container .main-container__contacts-list {
  gap: 10px;
}
.main-container .main-container__contacts-list .contacts-list__item a {
  display: flex;
  justify-content: center;
  align-items: center;
}
.main-container .main-container__contacts-list .contacts-list__item .icon {
  width: 20px;
  height: 20px;
  margin-right: 10px;
  display: inline-block;
  background-position: center;
  background-size: contain;
  background-repeat: no-repeat;
}
.main-container
  .main-container__contacts-list
  .contacts-list__item:nth-child(1)
  .icon {
  background-image: url("../assets/icons/telephone.svg");
}
.main-container
  .main-container__contacts-list
  .contacts-list__item:nth-child(2)
  .icon {
  background-image: url("../assets/icons/mail.svg");
}

.main-container .main-container__contacts-list .contacts-list__item .text {
  font-size: 2rem;
  line-height: 2.2rem;
  color: var(--dark-blue);
}
.main-container
  .main-container__contacts-list
  .contacts-list__item:nth-child(2)
  .text {
  font-weight: normal;
}

.main-container--open {
  transform: translateX(100vw);
}
.main-container--closed {
  transform: translateX(0);
}

@media (min-width: 980px) {
  .main-container,
  .main-container ul {
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }
  .main-container {
    position: static;
    transition: none;
    transform: translateX(0);
    width: 100%;
    height: 100%;
    padding: 0;
  }
  .main-container .main-container__menu-list .menu-list__item a,
  .main-container .main-container__contacts-list .contacts-list__item .text {
    font-size: 1.6rem;
    line-height: 2.1rem;
    font-weight: normal;
  }
  .main-container .main-container__contacts-list .contacts-list__item .text {
    font-weight: bold;
  }
  .main-container
    .main-container__contacts-list
    .contacts-list__item:nth-child(1)
    a {
    font-weight: bold;
  }
  .main-container
    .main-container__contacts-list
    .contacts-list__item:nth-child(1)
    .icon {
    display: none;
  }

  .main-container
    .main-container__contacts-list
    .contacts-list__item:nth-child(2) {
    display: none;
  }
  .main-container .main-container__menu-list {
    margin: 0 auto;
  }
}
</style>
