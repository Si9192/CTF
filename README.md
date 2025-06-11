# CTF
Building CI pipeline

Let's build a CI pipeline that will:

    Run tests on multiple Python versions
    Run Trivy vulnerability scanner over the codebase

Create a new file in the .github/workflows directory called ci.yml.
Step 1: Add the job to run tests on multiple Python versions

Add a job to the workflow that will run the developers' tests on multiple Python versions.

You can start simple: run a simple test with one Python version.

Then look at strategy and matrix to run the tests on multiple Python versions. 😉 Use versions 3.8, 3.9 and 3.10.

Bonus: developers asked you if you can run Flake8 to check the code quality too! Pfff, those developers...
Step 2: Add the job to run Trivy vulnerability scanner

Add a job to the workflow (meaning in the same file) that will run Trivy vulnerability scanner over the codebase.

Beware how to export the results of the Trivy scanner to the GitHub UI!
Building CD pipeline

Let's build a CD pipeline that will:

    Build a docker image
    Push the docker image to a container registry

Create a new file in the .github/workflows directory called cd.yml.
Step 1: Create a Docker Hub account

Create a Docker Hub account and connect it to your GitHub repository.
Step 2: Add a job to build the docker image

Create a job in the workflow that will build the docker image.

You have to create a Dockerfile.

Important note: we want the CD pipeline to run only if the CI pipeline has passed! (That's the whole point of a CI/CD pipeline, right?) Check workflow_run and the if condition in jobs.

There are multiple ways to do this. You could have used one file for both pipelines, but, you know, this is a good way to learn!  And it is a better practice to have one file per pipeline.
Step 3: Add a job to push the docker image to a Docker Hub repository

Add a new step in the job that will push the docker image to a Docker Hub repository.

You can either use the command line or the Docker Hub GitHub Action. It's up to you!

You will need to set the DOCKER_USERNAME and DOCKER_PASSWORD environment variables in the workflow in order to connect to your Docker Hub repository! In order to set secrets in a workflow, check this tutorial.
