---
title: 'Hashing Stencil props using nanoId'
excerpt: 'Using nanoId, I effectively hash to avoid id collisions.'
coverImage: '/assets/blog/hashing-ids/encryption-image.png'
date: '2023-03-02T05:35:07.322'
codeSnippet: '/assets/blog/hashing-ids/hashing-example.png'
author:
  name: Sam Pellegrene
  picture: '/assets/blog/authors/profile-pic.jpeg'
ogImage:
  url: '/assets/blog/mutation-observer/cover-image.jpg'
---

I recently developed a checkbox component using Stencil.js with the aim of ensuring accessibility compliance. While creating the component, I knew that optimizing focus states and using relevant attributes for screen readers were critical components in making the component accessible to all users, regardless of their abilities.

When it comes to focus states, I was aware that the browser already handles most of it quite well as long as the component is kept semantic. However, I also knew that screen readers were another story entirely. To ensure that screen readers can properly announce the component, certain attributes like for, aria-describedby, aria-checked, role, and id were essential.

To make the checkbox component more accessible for screen readers, I ensured that the id attribute was included. While passing the id as a prop to relevant attributes was a possible solution, it posed the risk of collision errors, especially when working on multiple pages across the app.

To mitigate this potential issue, I implemented nanoId to dynamically hash the id and use it as the default for the id prop. This allowed me to create an accessible and collision-free solution with minimal additional code.

In conclusion, ensuring that our components are accessible to all users is crucial in web development. By optimizing focus states and using relevant attributes for screen readers, we can create web applications that are usable and accessible to everyone.

---