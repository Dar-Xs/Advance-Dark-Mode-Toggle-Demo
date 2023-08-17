<script setup>
import { ref } from "vue";
const isDark = ref(false);
</script>

<template>
  <div
    :style="{
      display: 'flex',
      height: '100vh',
      flexDirection: 'column',
      justifyContent: 'center',
      alignItems: 'center',
      backgroundColor: isDark ? '#0B0B0B' : '#EFEFEF',
      transition: 'all 0.5s',
    }"
  >
    <!-- dark mode toggle -->
    <div
      :style="{
        width: '460px',
        height: '180px',
        borderRadius: '90px',
        backgroundColor: isDark ? '#202232' : '#4582b5',
        transition: 'all 0.5s',
        position: 'relative',
        overflow: 'clip',
      }"
      @click="isDark = !isDark"
    >
      <!-- clouds & stars -->
      <div
        :style="{
          position: 'absolute',
          width: '460px',
          height: '180px',
          transform: isDark ? 'translateY(100%)' : 'translateY(0)',
          transition: 'all 0.5s',
        }"
      >
        <!-- clouds back -->
        <div
          v-for="x in [
            [72, 23, 148],
            [72, 66, 154],
            [98, 102, 135],
            [98, 165, 103],
            [90, 216, 112],
            [122, 254, 80],
            [128, 309, 66],
            [150, 374, -11],
          ]"
          :style="{
            position: 'absolute',
            width: `${x[0]}px`,
            height: `${x[0]}px`,
            left: `${x[1]}px`,
            top: `${x[2]}px`,
            borderRadius: `${Math.floor((x[0] + 1) / 2)}px`,
            backgroundColor: '#ACCFE9',
            transform: isDark ? 'translateY(50%)' : 'translateY(0)',
            transition: 'all 0.75s cubic-bezier(0.73, 1.27, 0.54, 1)',
          }"
        ></div>
        <!-- stars -->
        <div
          v-for="x in [
            [16, 49, -130],
            [8, 56, -43],
            [10, 68, -58],
            [24, 92, -159],
            [16, 98, -107],
            [10, 102, -33],
            [14, 177, -96],
            [12, 195, -136],
            [20, 198, -56],
            [14, 235, -82],
            [30, 241, -135],
          ]"
          :style="{
            position: 'absolute',
            width: `${x[0]}px`,
            height: `${x[0]}px`,
            left: `${x[1]}px`,
            top: `${x[2]}px`,
            transform: isDark
              ? 'translateY(0)'
              : `translateY(-${3000 / x[0]}px)`,
            transition: 'all 0.75s cubic-bezier(0.73, 1.27, 0.54, 1)',
          }"
        >
          <svg :width="`${x[0]}px`" :height="`${x[0]}px`" viewBox="0 0 16 16">
            <path
              d="M8,0 C8,4.33491426 11.4478378,7.86454287 15.7508207,7.99619318 L16,8 C11.581722,8 8,11.581722 8,16 C8,11.581722 4.418278,8 0,8 C4.418278,8 8,4.418278 8,0 Z"
              fill="#FFFFFF"
            ></path>
          </svg>
        </div>
      </div>

      <!-- sun & moon -->
      <div
        :style="{
          position: 'absolute',
          margin: '15px',
          width: '150px',
          height: '150px',
          borderRadius: '75px',
          transform: isDark ? 'translateX(278px)' : 'translateX(0px)',
          transition: 'all 0.5s',
        }"
      >
        <div
          v-for="x in [
            [3.4, 3.6],
            [2.6, 2.8],
            [1.8, 2],
          ]"
          :style="{
            position: 'absolute',
            width: '150px',
            height: '150px',
            borderRadius: '75px',
            backgroundColor: 'rgba(255,255,255,0.1)',
            transform: isDark ? `scale(${x[0]})` : `scale(${x[1]})`,
            transition: 'all 0.5s',
          }"
        ></div>
        <div
          :style="{
            position: 'absolute',
            width: '150px',
            height: '150px',
            left: '0px',
            top: '0px',
            borderRadius: '75px',
            backgroundColor: isDark ? '#CBD0DB' : '#f5ce30',
            transition: 'all 0.5s',
            boxShadow:
              'inset 4px 6px 9px 0 rgba(255, 255, 255, 0.5), inset -2px -6px 7px 0 rgba(0, 0, 0, 0.5), 2px 6px 16px 0 rgba(0, 0, 0, 0.5)',
          }"
        >
          <!-- hole -->
          <div
            v-for="x in [
              [30, 97, 87],
              [48, 29, 63],
              [28, 61, 25],
            ]"
            :style="{
              position: 'absolute',
              width: `${x[0]}px`,
              height: `${x[0]}px`,
              left: `${x[1]}px`,
              top: `${x[2]}px`,
              borderRadius: `${Math.floor((x[0] + 1) / 2)}px`,
              backgroundColor: isDark
                ? 'rgba(161, 168, 185, 1)'
                : 'rgba(245, 206, 48, 0)',
              transition: isDark
                ? 'all 0.5s ease-out'
                : 'all 0.5s cubic-bezier(0, 0.5, 0, 1)',
            }"
          ></div>
        </div>
      </div>

      <!-- clouds -->
      <div
        :style="{
          position: 'absolute',
          width: '460px',
          height: '180px',
          transform: isDark ? 'translateY(100%)' : 'translateY(0)',
          transition: 'all 0.5s',
        }"
      >
        <!-- clouds front -->
        <div
          v-for="x in [
            [86, 33, 166],
            [86, 102, 150],
            [108, 162, 139],
            [150, 209, 151],
            [150, 266, 135],
            [150, 353, 82],
            [150, 385, 30],
          ]"
          :style="{
            position: 'absolute',
            width: `${x[0]}px`,
            height: `${x[0]}px`,
            left: `${x[1]}px`,
            top: `${x[2]}px`,
            borderRadius: `${Math.floor((x[0] + 1) / 2)}px`,
            backgroundColor: '#F6FDFF',
            transform: isDark ? 'translateY(100%)' : 'translateY(0)',
            transition: 'all 0.75s cubic-bezier(0.73, 1.27, 0.54, 1)',
          }"
        ></div>
      </div>

      <!-- inset shadow -->
      <div
        :style="{
          position: 'absolute',
          width: '460px',
          height: '180px',
          borderRadius: '90px',
          transition: 'all 0.5s',
          boxShadow: isDark
            ? 'inset 0px 7px 11px 0 rgba(0,0,0,0.9)'
            : 'inset 0px 7px 11px 0 rgba(0,0,0,0.7)',
        }"
      ></div>
    </div>
    <div
      :style="{
        padding: '14px 0',
        color: isDark ? 'white' : 'black',
      }"
    >
      {{ isDark ? "深色模式" : "浅色模式" }}
    </div>
    <a href="https://github.com/Dar-Xs/Advance-Dark-Mode-Toggle-Demo" target="_blank">
      <img
        alt="GitHub Repo stars"
        src="https://img.shields.io/github/stars/Dar-Xs/Advance-Dark-Mode-Toggle-Demo?logo=github"
    /></a>
  </div>
</template>

<style>
body {
  margin: 0;
}
</style>
