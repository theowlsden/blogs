# Continuous Integration & Deployment, a very non technical intro

Created: Apr 25, 2021

Last Updated: Apr 26, 2021

Tags: devops, beginners, todayilearned, codenewbie,

Cover Image URL: https://unsplash.com/photos/7r7-7RLdwCU

Photo by <a href="https://unsplash.com/@claytonrobbins?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Clayton Robbins</a> on <a href="https://unsplash.com/s/photos/process?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
  

Imagine this. You have a great app idea, you started the development and now you are ready to launch the beta version. You launch it to your waiting list and the first thing you see is that you have a bug when people are trying to log in.

<img src="https://media1.tenor.com/images/941def52f15ec9f071e378db898aab20/tenor.gif?itemid=15252602">

You go into your code and you realized that it was a silly mistake you did. One piece of code you added recently crashes another. In order to avoid that, here comes **Continuous Integration**.

## What is CI?

Continuous Integration (CI), is the first step of the DevOps coding philosophy and set of practices that streamline your application delivery. Implementing and executing CI means that you merge your code changes into your project's main branch and the changes will be validated against different tests. It can also be a specific branch for the different environments: testing, acceptance, and production.

Your application should be up to date, and more importantly with minimal bugs. How do you make sure that you have fewer bugs in your code? You guessed it, by testing your code. The same thing needs to happen when you make a code change. You need to test your code change to assert that everything is still working accordingly after the change. 

Implementing Continuous Integration means that at the end of each code change, you test the change against your whole application, make sure that nothing is broken. If something is broken, then you know beforehand and you can fix the bugs. This will reduce the chance of your application getting built and distributed with bugs. CI automates this whole process into a pipeline that automatically executes if the conditions are met ( e.g. you commit to the right branches).

<img src="https://ollesbloggtechome.files.wordpress.com/2019/04/coding-wey.gif">

Continuous Integration consists of four simple but important phases:
- Push your changes regularly.
- Test the application with the new changes.
- Fix any emerging merge issues or bugs that were introduced to the code.
- Once the code passes the tests, merge it with the main branch

With your CI pipeline in place, you can go ahead and make code changes to your heart's content. Once you have CI implemented for your project, you will be able to see that you can identify bugs and fix these bugs easier than before, and this will improve the quality of your application and since the testing is automated it will make your development process more efficient.

But you are not done yet. At the end of the CI pipeline, your code runs without any or minimal bugs, but you still have to deliver your application to the users. What good is updating the code without them getting the update in the app?

That is where the second part of CI/CD comes in. To handle the delivery of your application to your users you have two options:  namely Continuous Delivery & Continuous Deployment.

## Continuous Delivery
Most times when people are talking about CI/CD, they talk about Continuous Deployment. While CD stands for Continuous Deployment, it also has another meaning, namely Continuous Delivery. Continuous Delivery is the direct step after CI.

Continuous Delivery takes the tested code changes merged within the main branch and automatically builds the application and makes it ready for deployment. This automates the whole release process for your application. By automating the delivery of the updated application, you can choose how frequently the code update is pushed as a new release of the application to your different users (or environments). At the end of your Continuous Delivery pipeline, you have a compiled & build version of your application, and you can manually publish. 

## Continuous Deployment
Are you the type that wants to automate everything? then Continuous Deployment is for you.

Continuous Deployment goes one step further than Continuous Delivery. While with Continuous Delivery you decide when you deploy the new version of the application at the end of the pipeline, Continuous Deployment takes care of the deployment of the new version of the application to the users automatically.
 
This part of the CI/CD pipeline takes care of building and deploying the final updated version of the application to your different environments without any human intervention. This increases your productivity since there will be no need for you to plan a release date and everything is automated. The only time that the application is not deployed to the different environments is when a test fails in the CI.

![CI/CD flow](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/fhece2pzq8h2odpv1v2d.png)

Continuous Integration & Continuous Delivery/ Deployment sounds all good & dandy and in a real-world scenario, it will save you a lot of time in the long run. But one thing to notice is that it relies heavily on writing and using tests. In case you do not have the slightest idea of what tests are, check the previous post I created explaining Test Driven Development in a non-technical manner.

{% post https://dev.to/theowlsden/tdd-a-non-technical-intro-2o4k %}

I hope that you learned something new from this post and that you get an idea of how CI/ CD can improve your development process.🤙🏿