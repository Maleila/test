<script setup>
import WelcomeItem from './WelcomeItem.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
import SupportIcon from './icons/IconSupport.vue'
</script>

<script>
export default {
  data() {
    return {
      message: 'Button Powers',
      text: 'edit me',
      test: ''
    }
  },
  methods: {
    reverseMessage() {
      this.message = this.message.split('').reverse().join('')
    },
    buttonAction() {
      this.message = this.message.charAt(0)
    },
    enterText() {
      this.test = this.test.concat(this.testText)
    },
    notify() {
      alert('navigation was prevented.')
    }
  }
}
</script>

<template>
  <WelcomeItem>
    <template #icon>
      <DocumentationIcon />
    </template>
    <template #heading>Buttons!</template>

    {{ message }}

    <button @click="reverseMessage">Reverse</button>
    <button @click="buttonAction">Trim</button>

  </WelcomeItem>


  <WelcomeItem>
    <template #icon>
      <ToolingIcon />
    </template>
    <template #heading>Text field!</template>
    
    <input v-model="text"> {{ text }}

  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <EcosystemIcon />
    </template>
    <template #heading>Even better text field!</template>

    <input v-model="testText">
    <button @click="enterText">Enter</button>
    {{ test }}

  </WelcomeItem>

<WelcomeItem>
  <template #icon>
    <SupportIcon />
  </template>
  <template #heading>My Very Own Heading</template>

  Just a test of my own god-tier powers w Vue :) and maybe we'll add a little
  <a href="https://www.macalester.edu/" target="_blank" rel="noopener">link</a>
  just to see if we can get it working.
</WelcomeItem>
</template>
