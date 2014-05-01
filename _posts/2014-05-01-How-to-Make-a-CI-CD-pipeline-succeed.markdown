How to make a CI / CD pipeline succeed


What is a CI / CD pipeline and how does it work? Why is it important and how can you trust it? Those are some simple questions but the answers really make you think. I want to explore some ideas on how to make the pipeline succeed.

First what is a CI / CD pipeline. It is a way to progress changes from a requirements document (or bug report) to deployment for customer usage. It involves everything from requirements gathering to actually verifying its functionality. The important part of the pipeline is the speed of getting it to customers. 

The reason the CI / CD process is talked about so much is its all about fast turn around time, the faster the changes are deployed, the faster customers are using it, the faster you get more feedback. Having a setup to deploy your code faster (push button deployment) is great but it will not allow your company / team to reach CI / CD by itself.

Each company / team has there own set of issues to consider when deploying (no down time, no lost data, etc.). The way to combat the issues is to have a set of automated tests that are repeatable and can run quickly. That way if there are any issues with the change(s) they will be caught before they are deployed to production. 

Now I know I just said if you have automated tests that it will allow you to have a CI / CD pipeline, but that’s not everything. Having automated tests is not enough if you do not trust them. Most companies / developers know the benefits of automated unit tests (they test each part of your code an run quickly), but having a full integration test suite that can be run in production is still something a lot of companies are not pushing for. 

If you do not have a fully automated integration test suite for your production environment then you are only working on half the solution. Any company can build / buy an automated deployment system, but if you don’t have tests you can trust most companies wont want to utilize it. 

In summary most people have read the book “Continuous Delivery: Reliable Software Release through Build, Test, and Deployment Automation” by Jez Humble, and David Farley (if you have not I recommend you do that before doing any more work on CI / CD) and have tried to model there deployment pipeline around its suggestions. The part I see as being overlooked is a full integration test suite to run at the end of the deployment process.

