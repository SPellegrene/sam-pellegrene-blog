---
title: 'Vue Custom Elements and Mutation Observers'
excerpt: 'Using a mutation observer to efficiently watch changes to a child component living in the shadow dOM.'
coverImage: '/assets/blog/mutation-observer/cover-image.png'
date: '2023-02-20T05:35:07.322'
codeSnippet: '/assets/blog/mutation-observer/mutation-observer.png'
author:
  name: Sam Pellegrene
  picture: '/assets/blog/authors/profile-pic.jpeg'
ogImage:
  url: '/assets/blog/mutation-observer/cover-image.jpg'
---

I recently used vue-custom-elements to build a dropdown feature in a product. It's a new feature in Vue 3 that lets you create a component in Vue, register it as a custom element, and enjoy framework agnostic benefits while still using the Vue API.

To ensure that the dropdown was WCAG 2.1 compliant and able to take any other element as a child, including other vue-custom-elements, I had to get creative with how I approached the architecture of the component. In a native Vue environment, I would have used scoped slots, but because vue-custom-elements doesn't support them, I had to take a more code-intensive approach.

I built a parent dropdown component and a child dropdown item component. Within the parent, I set attributes on the child's component host using the mutation observer to watch for changes to the host's attribute collection. Once I properly observed, I could call my element crawling method. Then back to the parent, I called my key handling method that changes active index attribute values depending on the key event triggered. The final result is a compliant dropdown that can take any component/element and navigate accordingly.

---