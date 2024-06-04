# Introduction to CI/CD

> #### 11.1 Warming up
> 
> Think about a hypothetical situation where we have an application
> being worked on by a team of about 6 people. The application is in
> active development and will be released soon.
> 
> Let us assume that the application is coded with some other language
> than JavaScript/TypeScript, e.g. in Python, Java, or Ruby. You can
> freely pick the language. This might even be a language you do not
> know much yourself.
> 
> The points to discuss:
>  -   Some common steps in a CI setup include  _linting_,  _testing_, and  _building_. What are the specific tools for taking care of these steps in the ecosystem of the language you picked? 
>  -   What alternatives are there to set up the CI besides Jenkins and GitHub Actions? 
>  -   Would this setup be better in a self-hosted or a cloud-based environment? Why? What information would you need to make that
> decision?

In this hypothetical situation where have an application being worked on by a team of 6 people, the language I have chosen is Ruby. 

The tooling ecosystem of Ruby is robust when it comes to linting, testing and building. Starting with *linting*; The most popular linting tool is **Rubocop**, which ranks #32 by GitHub stars for Ruby projects, and is the #68 most downloaded Ruby Gem of all time, other alternatives are **Rufo** and **Standardrb**. 

Moving on to *testing*; The most popular are **Minitest** (#19 All Time Gem) which provides a complete suite of testing facilities supporting TDD, BDD, mocking, and benchmarking. The other option is **RSpec** (#24 All Time Gem) which is a Behavior Driven Development Testing Framework. The developer opinion seems to lean toward **Minitest** being simpler and **RSpec** being more complex and feature rich. 

Lastly we move on to *build* tools; since Ruby is an interpreted language a build tool is not necessary, but **Rake** is a popular CLI Build tool that allows you to define command line operations that are common during the build/deploy process such as file operations (creating, deleting, renaming, & moving files), publishing sites via FTP/SSH, and running tests. 

When it comes to CI alternatives to **Jenkins** and **GitHub Actions**, the most popular seems to be **GitLab CI** which can be self-hosted or cloud-based, other alternatives are **CircleCI** or services offered by cloud giants such as Microsoft (**Azure DevOps**), Amazon (**AWS CodeBuild**) and Google (**Cloud Build**). 

When it comes to our application , would it be better to setup CI in a self-hosted or a cloud-based environment ? I believe a cloud-based environment is more suitable since our team is small, we don't have any special requirements and the cost of rate/API limits would be cheaper than hosting our own server. Overall the information needed to make that decision, would be: 

 - *Cost optimization*: is it cheaper to host our own CI, or bill by usage
   on the cloud?  
  - *Reliability*: cloud-based CI is dependent on the
   hosting service uptime whereas with self-hosted you have to manage
   your own hardware.  
   - *Security*: using a self-hosted setup means that
   the entire environment is under your control, data and secrets are
   never exposed to at third party, whereas on a cloud-based setup your
   data and secrets flow through the service providers servers. 
   - *Simplicity*: is our use-case custom and complex in which case
   self-hosted allows us to tailor our needs or do we need something
   more simple that can be configured with predefined settings on cloud?
   - *Regulatory compliance*: depending on the jurisdiction in which you
   operate, there may be laws related to data and security that limit
   your options.