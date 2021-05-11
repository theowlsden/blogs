# Git-flow, non-technical intro.

Created: May 6, 2021 8:42 AM

Last Updated: May 11, 2021

Tags: Development, Devops, Todayilearned, Beginners

Cover Image URL: https://unsplash.com/photos/7r7-7RLdwCU

Photo by <a href="https://unsplash.com/@yancymin?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Yancy Min</a> on <a href="https://unsplash.com/s/photos/github?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>

Howdy DEV clan? 

We've all heard of the recommendation and best practice: "Use a version control for your project." While this is true, it might save you from F*CK-ups, not many blogs proclaiming the use of version control mention how to use it or the best way to use it.

Here comes Git-flow. Git-flow is a git workflow you can use to streamline your use of version control for your whole application. In today's post, I'll go over the basics of Git-flow and how it can improve your git-flow.

## What is git-flow?

Git-flow is a git workflow proposed in 2010 by this [post](https://nvie.com/posts/a-successful-git-branching-model/). This workflow is supposed to help you with your software development and DevOps practices. Git-flow defines a branching strategy and releases management for your software.

Git-flow uses git as its base (it's in the name!). Git was proposed for its distributed nature and "ease of use". Git allows for a simpler branching and merging mechanism compared to some other version control systems. More on [git here](https://git-scm.com/about).

### Git-flow branches

When you create a project and initiate git in it, you have by default your main branch (go on, try it don't be shy). In git-flow, this *main* branch HEAD (latest changes committed) should always contain the production-ready software.

You might be asking: If the main branch is for production-ready code, in which branch should I develop the application then? You guessed it! Your main development branch is called *develop*. The *develop* branch should always contain the latest changes that are ready for release (ready to be sent to production).

![https://nvie.com/img/main-branches.png](https://nvie.com/img/main-branches@2x.png)
[source](https://nvie.com/posts/a-successful-git-branching-model/)

To make sure that your *develop* branch only has the code that is ready to be sent to production, you need to separate your development into phases that work towards release. And guess what, git-flow has a solution for that.

Git-flow consist of three types of branches:

- **Feature branches**
- **Release branches**
- **Hotfix branches**

On a technical level, each branch is the same as the other. But for usage distinction, each type of branch has its specific use and is bound to strict rules for their originated branch (which branch they can be branched off) and their merging targets (which branch they are allowed to branch into).

![https://nvie.com/img/git-model.png](https://nvie.com/img/git-model@2x.png)
[source](https://nvie.com/posts/a-successful-git-branching-model/)

### Feature branches

Feature branches are used to develop well, features. Do you want to develop the login feature of your software? You do that in the feature branch. You use feature branches to develop the features you want to add to your software, for a new release or a distant one (maybe you just want to set the base to develop and publish later). 

The feature branch should always branch off from the *develop* branch. Why? So that you have the latest version of your to work with. Likewise, the feature branch should always be merged into the *develop* branch, this will make the feature ready to be released.

### Release branches

Release branches, well they are there to do final tinkering on a release before it goes to production. In these branches, you make minor fixes and final tinkering. Why do you use a release branch if your *develop* branch has the latest code?

Glad you asked (even if you didn't), this is to separate the release from the concurrent development. Let's say you finished three features at the same time (thus merged them into the *develop* branch), but you want to release only one. You create a release branch for that specific feature, do the final tinkering, and merge that to the main branch. Easy peasy lemon squeezy, you separated the release of the feature while keeping your *develop* branch available to changes from new features.

Since you are working with code that is ready for release, you can only make a *release* branch by branching from *develop*. When you are done with the branch, you must merge it into the *main* branch and release the code and into the *develop* branch (so that your develop branch has the latest changes).

### Hotfix branches

Finally, we have hotfix branches. They have the same functionality as release branches, prepare your code for production, but they are used specifically for unplanned changes/ improvements. 

Imagine you tested your software against the major ways your software can break, and it passes them all and you released the new feature. Just a day or two after the release, your users start complaining that they get X instead of Y when they click on a button. 

To fix that bug, you don't need to create a feature branch, then merge it into *develop* and create a release branch. No! you create a hotfix branch from your main branch and fix that bug, hence *hotfix*. After fixing the bug in your code, you must merge the changes into the *develop* branch and the *main* branch for production.

![https://thumbs.gfycat.com/ClearcutWeightyHartebeest-size_restricted.gif](https://thumbs.gfycat.com/ClearcutWeightyHartebeest-size_restricted.gif)

So, there you have it. Git-flow is a very strict workflow for version controlling your project, and to some, it might look over-engineered and daunting. I recommend to not follow it to the letter, pick bits and pieces, and Frankenstein your way to a development structure that you and your team can easily work with and integrate into your projects.

I hope that you learned something from this post. Go on and structure your side projects!🤟