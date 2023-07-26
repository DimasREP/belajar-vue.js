<script setup>
import { Navbar, NavbarLogo, NavbarCollapse, NavbarLink } from "flowbite-vue";
</script>
<template>
  <Navbar>
    <template #logo>
      <NavbarLogo
        link="https://www.google.com/"
        alt="Flowbite logo"
        image-url="https://i.pinimg.com/474x/bb/6e/2a/bb6e2a77bd60d1c19cb7ebe74cfed149.jpg"
      >
        Zee Store
      </NavbarLogo>
    </template>
    <template #default="{ isShowMenu }">
      <NavbarCollapse :isShowMenu="isShowMenu">
        <NavbarLink isActive link="#">Home</NavbarLink>
        <NavbarLink link="#">Tentang</NavbarLink>
        <NavbarLink link="#">Contact</NavbarLink>
      </NavbarCollapse>
    </template>
  </Navbar>
</template>
