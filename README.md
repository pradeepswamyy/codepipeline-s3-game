    **STEPS TO FOLLOW** 
    
**Step 1:** Fork a GitHub repository containing the game's source code to your personal GitHub account for independent development.

By forking a repository, you create a copy of the original repository under your own GitHub account. This enables you to make changes to the codebase without affecting the original repository. Once you have made changes, you can submit a pull request back to the original repository to propose incorporating those changes into the main project.

**Step 2:** Create an S3 bucket on AWS to serve as a virtual hard drive for storing game files and enable static website hosting for public access.

An Amazon Simple Storage Service (S3) bucket provides scalable object storage for data backup, archival, and analytics. For this project, we use an S3 bucket to host the static assets of the game, such as images, stylesheets, and scripts. Enabling static website hosting makes the contents of the bucket accessible via HTTP(S), making the game available for players to access over the internet.

**Step 3:** Configure a pipeline in AWS CodePipeline to connect your GitHub repository with the S3 bucket, allowing automated updates to the game files when changes are pushed to the repository.

AWS CodePipeline is a continuous delivery service that automates the release process for applications and infrastructure updates. With CodePipeline, you can create a pipeline that includes stages for building, testing, and deploying your application. In this case, we configure CodePipeline to monitor your GitHub repository for changes and then automatically deploys new versions of the game to the S3 bucket.

**Step 4:** Skip the build option since the game does not require compilation, thus conserving time and resources.

When configuring the CodePipeline, there is an optional build stage where you can compile and package your application before deployment. However, for this simple web-based game, no compiling or packaging is required. Therefore, we skip this step to save time and resources.

**Step 5:** Update the game version by editing the `index.html` file in your GitHub repository, which triggers an automatic update in the S3 bucket and displays the newest version of the game to users visiting the site.

Once the CodePipeline is set up, every change you make to the `index.html` file in your GitHub repository triggers an automatic update in the S3 bucket. Players accessing the game via the URL associated with the S3 bucket will immediately see the updated version of the game. This streamlines the development process, eliminating the need for manual uploads and providing quick turnaround times for bug fixes and feature enhancements.



