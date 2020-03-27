# Onboarding

## About the project

An app pretending to track the health of the user and his neighborhood.
A system that detects symptoms anonymised, and allows the collection of the general health of the population to help healthcare entities to make better decisions.

## Team and Slack channels

### Product
- @PedroFortuna-Jscrambler_Security_Linux_Dev_Ideas for an invite
- @RuiCosta_Covidografia_Codavel 

### Infrastructure and Legal
- @Paulo Cunha - infrastructure/tracovid - Velocidi/CEO

### Development
- @Luís Borges_Covidografia_dev_codavel
- @Ricardo Fernandes_Software_bitmaker 

If you have a dev question, please use either this channel or one of the more specific channels:
>`#covidografia-web_luis-borges`
>`#covidografia_backend-luis_borges`
>`#tracovid19_devops-andre_carvalho`
>`#covidografia-qa_testing_userfeedback`
*ask @Luís Borges_Covidografia_dev_codavel in slack to join the channels*

If you have product suggestions, new features or improvements, please do it so here:
> `covidografia-productmanagement` 
*(ask @PedroFortuna-Jscrambler_Security_Linux_Dev_Ideas for an invite)*

Any infrastructure related question, please bug @Paulo Cunha - infrastructure/tracovid - Velocidi/CEO


## First contribution

This is an open source project. Therefore the source code is freefly available and new contributors are always welcome! 

### Where to start?

All the repositories are under the organization **tech4covid19** github account at https://github.com/Tech4covid19. 

For the time being, two repos are owned by Covidografia:
- [Frontend](https://github.com/Tech4covid19/trackovid19-web "Frontend") 
- [Backend](https://github.com/Tech4covid19/trackovid19-backend "Backend") 

All the issues are listed in the [kanban board](https://github.com/orgs/Tech4covid19/projects/2). Described with more details below.


### Design and UI/UX

This is the place where the UI is defined so everyone knows exactly what to build. When developing UI features, please use the exact copy you find in the mockups, since they've already been validated by the product, marketing and legal teams.

Url: https://www.figma.com/file/BfK7HtPsvxZAwZLg1ebz2u/Covidografia?node-id=0%3A1

## Project landscape

### How does it work?

![Diagram](https://i.imgur.com/wVdobgH.png)

### Frontend

The frontend repository can be reached at https://github.com/Tech4covid19/trackovid19-web and comprises the source code of both the web app and a first take on the mobile app. 

Please refer to the README files for further information about those projects.

#### Web app

##### Stack

- Angular
- Javascript

##### Current status

[Current version in production](https://app.covidografia.pt "Covidografia")

![Login](https://i.imgur.com/2P3e30v.png)

![Dashboard](https://i.imgur.com/P3EvdUn.png)


#### Mobile app (**on hold**)

From the beginning the team decided that providing a mobile app could reduce the friction for the user. This was potentially confirmed later with the first release of the [website](https://covidografia.pt "Covidografia"), being accessed from a big majority of the audience with mobile devices as source.

At the beginning the mobile app was prioritized with the same level as the website. Due to well known problems with a similar mobile app submited to play store and apple store, later identified as ransomware and removed, we **postpone the mobile app release** and, for now, is **on hold**. We will get back to it soon.

##### Stack

- Angular
- Ionic
- Javascript

##### Current status

The mobile app has the skeleton and some views implemented, but is far from ready. 

#### Backend

The backend repo is available at https://github.com/Tech4covid19/trackovid19-backend. Please refer to the project's README file for instructions on how to setup the project for development.

## Project governance

### Creating issues

Issues should be created under the repo they make more sense and should be prefixed with either `[backend]` or `[frontend]` depending on the repo you picked.

Ex. A frontend related issue, say `fix login copy`, should be created under the frontend repo, and should be named: `"[frontend] fix login copy"`.

After creating the issue one should go to the `Projects` section on the right pane and select `"Tech4Covid19"`. This will make the issue available in the project's [Kanban board]( https://github.com/orgs/Tech4covid19/projects/2).

### Project board

There's a Kanban board containing all issues that have been selected for development for the project available at https://github.com/orgs/Tech4covid19/projects/2.

All issues entering the board are placed in the **Backlog** column by default.

The **TO-DO** column contain the issues that were selected for development, and are prioritized from top to down. **This means that the top issues have highest priority.**

**Before coding, the developer should start with the following 3 steps**:
 - pick one issue from the **TO-DO** column, 
 - assign the issue to him/she 
 - move the issue to **In Progress** column

**The 3 steps above are very important to avoid repeated work and useless effort!**

**The “Backlog” issues are not ready to implement. Don’t pick one from here.**

**Notes:**
> No coding should be performed unless the above 3 steps were completed.
> Only issues from the **TO-DO** column should be selected.
> Issues should be move to the **In Progress** column once started and to the **Review** column upon submission for review (via Pull Request).

### Git workflow


#### Branches

All projects have a `develop` and a `production` branch which are meant to organize the development and deployment lifecycle.


#### Develop and production

When developing new features or fixing bugs one should create a branch out of the `develop`, which is the default branch. The name of these branches should have the following structure:
```
issue/<issue-number>
```

Ex. Let's create the branch for working on issue #34:
```
git checkout -b issue/34
```

then let's synchronize it with the server:

```
git push --set-upstream origin issue/34
```

#### Pull Request

As soon as you finish coding you should push your changes to the server and create a PR - *Pull Request*.

Make sure you synchronize (merge) your branch with the latest state of the `develop` branch before making the PR, otherwise it won't be accepted.

Accepted PRs are automatically built and deployed to staging.

#### Pull Request close the issue

Please, use the following comment in PR to link the respective issue:

> closes #<issue_number>

Moreover, add a couple of lines that describes how do you implement, features added or bugs fixed in the PR.

#### Accept a Pull Request & Code Review

Once a Pull Request is open it needs to be approved by **2 developers** before being available to merge. After the approval of those **2 developers**, the PR to `develop` branch could be accepted by everyone.

#### Commit messages

Try to describe as much as possible information to the commit messages and avoid repetitive broad messages like "added prints" or "minor changes"


#### Deployment

The deployment has 3 main stages, completely separated:
- Production
- Staging
- Development

##### Production

The production stage is the one publicly available. The frontend is available at `https://app.covidografia.pt` and the backend is available at `https://api.covidografia.pt`


##### Staging

The staging stage is used to test new features and bug fixes. Is publicly available, but it is only for testing usage. The frontend is available at `https://staging.app.covidografia.pt` and the backend is available at `https://staging.api.covidografia.pt`

##### Development

The Development stage is a special stage created to test only frontend in `localhost`. This environment is necessary because the redirection after login in the backend should assume that frontend is running `localhost`. This is the environment to run when you are coding in the frontend.

The address of the backend is `https://dev.api.covidografia.pt`


**Attention!** To use this environment you need 2 extra steps:

- Run the browser with [CORS disabled](https://alfilatov.com/posts/run-chrome-without-cors/)
- Use the following fake credentials to login with facebook:
    - user: `open_rlwzmij_user@tfbnw.net`
    - pass: `covidografia19`


