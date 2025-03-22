<script setup>
import lost_world_img from '@/assets/portfolio/the-lost-world.png'
import avatar_img from '@/assets/avatar.jpg'
import malalearn_splash from '@/assets/portfolio/malalearn.png'
import medrec_img from '@/assets/portfolio/medrec.png'

import { useDisplay } from 'vuetify'
import AppFooter from "~/components/AppFooter.vue";

const {name, smAndDown} = useDisplay()

const languages = ["Rust", "Go", "C#", "Dart", "Python", "Javascript", "Typescript"]
const frameworks = ["Vue.js", "React.js", "Flutter", "Unity", "Godot", "Raylib", "Avalonia UI", "Blender", "Node.js"]
const projects = [
  {
    image: lost_world_img,
    title: "The Lost World",
    description: "A 3D platformer made using Unity and C# made for a game jam on itch.io",
    link: "https://t-more1010.itch.io/lost-world"
  },
  {
    image: malalearn_splash,
    title: "Malalearn",
    description: "An offline video learning app made using C# and Avalonia UI",
    link: ""
  },
  {
    image: medrec_img,
    title: "MedRec",
    description: "An electronic medical record storage app made using Flutter, Go and SQLite",
    link: ""
  },
  {
    image: "",
    title: "Duplicheck",
    description: "A cli tool for duplicate file checking and elimination implemented using Golang",
    link: "https://github.com/TimothyKandiado/duplicheck"
  },
  {
    image: "",
    title: "NovaLang",
    description: "A dynamically typed programming language that compiles down to register based vm bytecode implemented using Rust",
    link: "https://github.com/TimothyKandiado/NovaLang"
  },
  {
    image: "",
    title: "NyengoApp",
    description: "A weather forecasting web app built using Vue.js, Go, and MongoDB",
    link: ""
  },

]

const experience = [
  {
    title: "Freelance Desktop App Developer",
    description: "Creating a desktop app called MedRec for storing medical records electronically using Flutter, Go, and SQLite ",
    color: "blue",
    dot_icon: "mdi: mdi-monitor",
    purpose_icon: "mdi: mdi-hospital-box",
    date: "Oct 2023 - Mar 2024"
  },
  {
    title: "Freelance Desktop App Developer",
    description: "Creating a desktop app called Malalearn that runs on Windows, and Raspberry Pi 4+ for distributing educational videos to remote areas",
    color: "green",
    dot_icon: "mdi: mdi-dot-net",
    purpose_icon: "mdi: mdi-school",
    date: "June 2024 - Oct 2024"
  },
  {
    title: "Freelance Web App Developer",
    description: "Building a Progressive Web App called NyengoApp for weather forecasting",
    color: "purple",
    dot_icon: "mdi: mdi-vuejs",
    purpose_icon: "mdi: mdi-cloud",
    date: "Nov 2024 - Feb 2025",
  },
  {
    title: "Software Developer",
    description: "Employed by Tecnozone IT solutions as a Software Developer",
    color: "blue",
    dot_icon: "mdi: mdi-monitor",
    purpose_icon: "mdi: mdi-code-braces",
    date: "Feb 2025 - Present",
  },

]

const isSmallScreen = () => {
  const size = name.value
  return size === 'sm' || size === "xs";
}
</script>

<template>
  <!-- Navigation Bar -->
  <v-app-bar app>
    <v-toolbar-title>Timothy Kandiado</v-toolbar-title>
    <v-spacer></v-spacer>

    <v-btn href="#about">About</v-btn>
    <v-btn href="#portfolio">Portfolio</v-btn>
    <v-btn href="#experience">Experience</v-btn>
    <v-btn href="#contact">Contact</v-btn>
  </v-app-bar>

  <!-- Hero -->
  <v-container id="hero" class="d-flex align-center justify-center min-height-100vh pt-16">
    <div class="fill-height">
      <div class="d-flex align-center justify-space-around">
        <v-avatar size="200">
          <v-img :src="avatar_img" alt="Timothy Kandiado"></v-img>
        </v-avatar>
      </div>
      <h1>Timothy Kandiado</h1>
      <p class="py-6"> Chemical Engineer | Game Developer | Fullstack Web Developer | Desktop & Mobile App Developer</p>
      <v-btn large href="#portfolio"> View My Work</v-btn>
    </div>
  </v-container>

  <!-- About -->
  <v-container id="about" class="py-12 h-25 elevation-20">
    <v-row>
      <v-col cols="12" md="6">
        <h2>About Me</h2>
        <p class="text-body-1">
          I'm a Chemical Engineering graduate with a passion for software and game development.
          I love combining creativity and problem-solving to build impactful applications
          and immersive experiences.

          Let’s connect!
        </p>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" md="6">
        <h3>Languages</h3>
        <v-chip-group column>
          <v-chip v-for="item in languages">{{ item }}</v-chip>
        </v-chip-group>
      </v-col>
      <v-col cols="12" md="6">
        <h3>Frameworks</h3>
        <v-chip-group column>
          <v-chip v-for="item in frameworks">{{ item }}</v-chip>
        </v-chip-group>
      </v-col>
    </v-row>
  </v-container>

  <!-- Portfolio -->
  <v-container id="portfolio" class="py-12">
    <h2>Portfolio</h2>
    <v-row>
      <v-col cols="12" md="4" v-for="(project, index) in projects.slice(0, 3)" :key="index">
        <v-card>
          <v-img :src="project.image" height="200px" cover></v-img>
          <v-card-title> {{ project.title }}</v-card-title>
          <v-card-text> {{ project.description }}</v-card-text>
          <v-card-actions v-if="project.link">
            <v-btn :href="project.link" target="_blank">View</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" md="4" v-for="(project, index) in projects.slice(3, 6)" :key="index">
        <v-card>
          <v-img :src="project.image" height="200px" cover></v-img>
          <v-card-title> {{ project.title }}</v-card-title>
          <v-card-text> {{ project.description }}</v-card-text>
          <v-card-actions v-if="project.link">
            <v-btn :href="project.link" target="_blank">View</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>

  <!-- Experience -->
  <v-container id="experience" class="py-12 elevation-20">
    <h2>Experience</h2>
    <v-timeline :side="smAndDown?'end':'opposite'">
      <v-timeline-item
          v-for="(item, index) in experience.reverse()"
          :key="index"
          :dot-color="item.color"
          :icon="item.dot_icon"
          fill-dot
      >
        <template v-slot:opposite v-if="!smAndDown">
          <span :class="`text-${item.color}`">{{ item.date }}</span>
        </template>
        <v-card max-width="400" v-ripple>
          <v-card-title :class="`bg-`+item.color+`-lighten-3`">
            <v-icon class="me-4" :icon="item.purpose_icon"></v-icon>
            <h3 class="font-weight-light">
              {{ item.title }}
            </h3>
          </v-card-title>
          <v-card-text> {{ item.description }}</v-card-text>
        </v-card>
      </v-timeline-item>
    </v-timeline>
  </v-container>

  <!-- Contact -->
  <v-container id="contact" class="py-16">
    <h2>Contact</h2>

    <a>
      <v-icon icon="mdi: mdi-email"></v-icon>
      kandiadotimothy@gmail.com
    </a>
  </v-container>

  <AppFooter />
</template>
