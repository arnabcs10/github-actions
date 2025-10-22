# Why custom actions?
- Multiple steps can be grouped into a single custom action.  We use custom actions to encapsulate complex/reusable logic for our web project deployment pipeline.
- This allows us to maintain cleaner workflow files and promotes reuse across multiple workflows or repositories.
- This also helps other teams in our organization to easily adopt and adapt these actions for their own projects.

# Types of Custom Actions

1. Javascript Action
 - Here we develop the action logic in javascript, and when invoked a js code is executed.
 - JS packages can be used

2. Docker Action
 - Here we create a dockerfile with our required configuration & github will create a docker container based on your dockerfile image.
 - Performs any tasks of your choice with any language.

3. Compisite Actions
 - We combine multiple workflow steps in one single action
 - Allows for resusing shared steps
 - We can create separate public/private repos for all our required github actions and refer them in our project whenever required.
 - Or we can create our actions on the project itself.