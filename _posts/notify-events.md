---
title: 'Building A Jenkins pipeline'
excerpt: 'Automating my build pipeline to future proof my personal project.'
coverImage: '/assets/blog/jenkins-pipeline/jenkins-pipeline.png'
date: '2023-03-06T05:35:07.322'
codeSnippet: '/assets/blog/jenkins-pipeline/carbon.png'
author:
  name: Sam Pellegrene
  picture: '/assets/blog/authors/profile-pic.jpeg'
ogImage:
  url: '/assets/blog/mutation-observer/cover-image.jpg'
---

Recently, I've been working on a personal project involving stremalining WCAG Accessibility requirements for developers. In order to future proof my CI, I created a Jenkins pipeline to automate the build and test process.

The pipeline script I wrote consists of four stages: Verify Branch, Build, Test, and Send Notifications. Since this project isn't hosted publically, I haven't configured the webhook to allow auto build per commit. But this is something I will write in once I host my tool.

In the Verify Branch stage, the pipeline checks which branch the commit was made on. This is useful because sometimes, we may want to run different actions depending on the branch, for example, only run tests on the development branch.

Next, in the Build stage, the pipeline installs the project dependencies using npm. The post block ensures that if there is an error during the dependency installation process, a notification is sent to the specified recipient.

The Test stage runs the unit tests for the project using the npm run test command. Once again, if the tests fail, a notification is sent to the recipient.

Finally, in the Send Notifications stage, I'm using Notify.events to email a message indicating that the build process was successful.

The Jenkins pipeline I created for this personal project helped me save time and effort by automating the build and test process. It also ensured that errors were detected early in the development process, allowing me to fix them before they cause major issues down the line.

One thing I learned from this experience is that building a pipeline can be challenging. It requires a good understanding of the tools and technologies involved and a lot of trial and error. However, with patience and perseverance, it's possible to create a pipeline that is tailored to your specific needs.

Overall, I am glad that I took the time to create a Jenkins pipeline. It was a valuable learning experience, and I now have a tool that I can use for future projects to improve my development process.

---