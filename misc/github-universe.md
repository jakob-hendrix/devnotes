# Notes from Github Universe

Conference on 11/13 and 11/14.

## Main Takeaways

* get a CI/CD workflow, pushing personal dotnet core website through Travis CI and into Digital Ocean
* question assumptions. Can we have access to the MOVEit DMZ via WinSCP. Is Central a requirement?
* CI/CD should be possible for DBC, script, and cmd code since we have SSH access. Possibly through Bamboo? Talk to James
* github changes that are cool
  * actions/packages
  * enhanced notifications
  * issue templates
  * repository templates
* move to a mono-repo structure that organizes around projects and code structures
* rework the gitflow
* move back to `master` as the production branch
  * `feature_*` and `bugfix_*` branches
  * correct commit process
    * `git pull` always should be first
  * reconsider Github Desktop as the primary git tool. Apparently it has been reworked quite a bit and it might be a better way to introduce people to the technology

### Day 1

#### 10:30 am

> Actions Packaged: Use GitHub Actions and GitHub Package Registry for CI/CD of any app, package, and service
This session will focus on the latest updates for GitHub Actions and GitHub Package Registry, and how to use them to build, test, and deploy your code. We’ll also walk through examples of repositories using GitHub Actions and GitHub Package Registry for their production CI/CD with multiple different configurations. At the end of this talk, you’ll have an end-to-end understanding of GitHub Actions and GitHub Package Registry, as well as how to use them with your project.

Notes: Github actions will allow us to begin building out automations for each repository. We can begin building out a suite of Continuous Integrations (CI) (DBC compile) and Continuous Deploymnets (CD) (copy to batch directories and to the rollin directories on AIX via SSH)

#### 11:25 AM

> "Good code documents itself" and other lies: Changing work culture through documentation
Most developers have heard “good code documents itself” or “documentation outdates easily, the code does not” at some point. This is an excuse to not write documentation or justify the absence of it. In my work with many teams, the lack of documentation is often a symptom of high technical debt.
>
> What if we could turn this around and use documentation like a driver for positive culture change and start paying the critical technical debt? This approach not only helps teams to faster identify areas that need critical support but also brings more empathy to the table.
>
> In this talk, Tania draws on experiences using documentation as a weapon for positive culture and process change in machine learning and scientific computing environments. She focuses on the processes and approaches that enable the creation of documentation for data scientists, infrastructure, and software engineering teams, and clients.
>
> By the end of the talk, you'll learn efficient techniques to make documentation a first-class citizen in your development cycles—and leave with one or two tricks to convince even the most reluctant developer to document code.

Notes: completion of documentation is a necessary part of any change. This may be hard to enforce without locking down how code is moved into production. If we can get the CD part working, then all changes have to go through the Git workflow

#### 1:15 pm

> Insights into GitHub Enterprise: How IBM tracks social coding
How do you track whether GitHub is supporting and increasing the frequency of good coding behaviors like code review, continuous integration, and social coding for your company? When faced with this problem, IBM dove into their instance of GitHub Enterprise. In doing so, they gained insight into how IBM's internal coding practices within GitHub have developed since 2015 and information about the health of the ecosystem that has sprung up within GitHub. In this talk, you'll hear about their methods of investigation that can be applied to any organization and enterprise-specific datasets to apply business context to the data.

Notes: Github enterprise has a database that can be queried and analytics run against it. Cool.

#### 1:15 pm

> Insights into GitHub Enterprise: How IBM tracks social coding
How do you track whether GitHub is supporting and increasing the frequency of good coding behaviors like code review, continuous integration, and social coding for your company? When faced with this problem, IBM dove into their instance of GitHub Enterprise. In doing so, they gained insight into how IBM's internal coding practices within GitHub have developed since 2015 and information about the health of the ecosystem that has sprung up within GitHub. In this talk, you'll hear about their methods of investigation that can be applied to any organization and enterprise-specific datasets to apply business context to the data.

Notes: This was a fun bit of history on the transformation of code inside the Ford company. It also intorduced the concept of *fail-fast* - the idea that builds should abort on first failure to prevent wasted processing

#### 3:20 pm / Wednesday Nov 13

> Secure container development workflows with Anchore and GitHub Actions
Containers are a driving force behind code reuse for businesses of all sizes, allowing developers to choose from a variety of software sources when they’re building an application. However, containers can sometimes introduce unwanted security and compliance flaws. GitHub’s Steve Winton and Anchore’s Zach Hill will discuss how users can now check containers for known vulnerabilities and configuration issues automatically, thanks to Anchore and GitHub Actions. Plus, they’ll show you some ways you can integrate this new product into your development pipeline.

Notes: This is was a cool demo of a product. Anchore sits in the CI/CD pipeline after the test and build steps and anaylzes dependcies hierarchies, especially for vulns

#### 4:15 pm

> GitHub Archive Program Partner Panel
Join the GitHub Archive Program partners for a deep dive into their unique approaches and technologies used to preserve the world’s knowledge for future generations.

Notes: super nifty, if unrelated, look into the need to archive code for the very long terms. Think the seed vault in Svalbard, Norway

---

### Day 2

#### 9:00 am

> Keynote: security

Notes: lots of good information here regarding Github's place in the bug bounty ecosystem. In Github, if not Github enterprise, there will be some very cool integrations with the formal security/hacker entities

#### 10:30 am

> Applying the GitHub security development lifecycle to your open source project
Session description coming soon.

Notes: more security information. This will be more applicable as we start developing using open source tools

#### 11:25 am

> Panel: Embracing open source in risk-averse organizations
This fireside discussion with open source leaders with experience in some of the largest organizations in the world will expose achievements, best practices, and some pitfalls along the way to embracing open source, even in risk adverse environments. They'll share the successes and challenges they’ve overcome as they’ve integrated open source technologies, methods, and culture into its daily business operations. You'll also hear insights from the State of Financial Open Source Survey (sponsored by the FinTech Open Source Foundation and GitHub) to better understand how industries, specifically financial services, are adopting open source.

Notes: This was a very good discussion between two middle-mgmt types that push open-source in {some bank} and Verizon Media, and another person that works in an organization that applies presusre to finacial tech businesses to move towards OS. There are 3 conversations that will be had, and you have to have them with the right person (depending on which they want to discuss). 1. Fear 2. Love 3. Money/Risk. This was largey more focussed on taking internally dev-ed apps and makign them open source. So the idea of **Day 2** applied - hwo to maintain and not suffer reputaiton damaage form shit code

#### 1:15 pm

> Machine learning operations with GitHub Actions and Kubernetes
From automating mundane tasks to reducing inefficiencies in developers’ workflows, machine learning has the potential to scale your team’s results like never before. However, the practice of deploying machine learning for enterprises is relatively new. In this talk, Hamel and Jeremy will demonstrate how GitHub Actions and Kubernetes can be used to orchestrate machine learning workflows in new ways that increase transparency and reliability of these applications. By borrowing best practices and technologies from DevOps, they’ll help you learn how to deploy machine learning solutions with confidence.

Notes: N/A. This was a presentation on a CI/CD tools developed by Google for ML, which invoilves a more elaborate workflow than non-ML applications.

#### 2:10 pm

> Advanced GitHub Actions: workflows for production grade CI/CD
Join GitHub Product Managers, Kayla Ngan and Edward Thomson, for a demo-packed session on GitHub Actions. After a short primer on advanced features, see how to deploy to GitHub Packages, auto-merge dependabot pull requests, and deploy a web service. This talk will inspire you to get creative with how you use Actions in your daily workflows.

Notes: Github actions are cool. They can be used to activate very elaborate actions, including javscript activity (the example deleted a recently made comment and replaced it with a humourous image)

#### 3:20 pm

> What does it take to transform a federal agency to a lean, product-focused enterprise?
By shifting the focus away from traditional, plan-driven “project management” (e.g., cost management, schedule management, etc.) towards a more user-driven product management approach (e.g., user research, minimum viable products, etc.), the VA has been working to create the best digital experience for Veterans and business customers. Learn how VA went about this massive cultural shift -- to making human centered design (HCD) a requirement, not a “nice to have.”
>
>There’s no point in delivering something on-time and on-budget--if it’s the wrong thing.

Notes: This was the best presentation. Very insiprational. The speaker was a part of the US Digital Service (a program established under Obama to modernize the Federal goveemenrt tech stacks). They completely reworked how the VA interacts with venterans, making plenety of mistakes along the way. Lots pof notes taken during this presentation. The main takeways were that the MVP model can work,but it's important to get buyin from above using qulatative examples, not just quantataitve (human-cenerted). Also, the push should be for a Product > Project perspective

#### 4:15 pm

Deep dive into GitHub's newest features
GitHub has shipped a lot of features in the past few months that you might not even know about. In this talk, I will show you some features that we’ve added, how you can use them as part of your day to day workflows, and dive a bit deeper into some of the new features we shared in our keynote.

Notes: There's a lot fo cool stuff coming down the pipeling. Notofications, repo templated, issue templates. Lots of quality of life improvements that we should get when/if our Enterpirse server is updated. Github.com has it now.

## Transcribed Notes

TODO:
