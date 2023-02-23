# ~2023/02/23

---

# Various Runtimes, Various Conflicts

I switched from using `puppeteer` to `playwright` as my headless browser in order to bypass fingerprinting. It worked well on my local machine, but when I deployed my code on cloud infrastructure (ARM, Ubuntu 22.02), it threw many conflicts. This experience taught me the importance of runtime abstraction using containers.

# Focusing on Development

I also helped a friend who was struggling with deploying his Discord bot on `AWS` because he was not familiar with cloud infrastructure services. Previously, he had deployed his bot on `Heroku`, which is a much simpler cloud application platform.

This experience made me realize the need for a deployment pipeline.

# Conclusion

I will create a Docker image and then use a continuous deployment pipeline (CD pipeline) using Github Actions, Jenkins, or another tool.
