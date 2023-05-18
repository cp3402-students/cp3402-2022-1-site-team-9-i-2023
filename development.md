# CP3402 Assignment 2 - Group I - Development Workflow

## Development Workflow Description

1. Create a wireframe prototype
2. Experiment and test on a local Wordpress install
3. If needed, deploy and test on a staging instance
4. Deploy on production instance
5. Commit changes to git for version control

## Applications and Processes

Our site deployment for this project takes advantage of a number of programs, applications, and working environments to
facilitate
the creation and editing of the site theme and to push those changes to the development (test) site and finally to the
live site. The applications
used, a brief description on how (and why) they are used in this particular project, and a link to acquire them can be
found below:

### Theme Development

**PhpStorm**: PhpStorm is a cross-platform IDE created by JetBrains used to edit various types of code (PHP, HTML,
Javascript, etc). In this project it is the primary means of editing the theme and was chosen due to its popularity and
its various "Wordpress Aware" features. PhpStorm can be downloaded here: https://www.jetbrains.com/phpstorm/

**_S (underscores):** Underscores is a starter theme and designed to be edited to create new CMS themes. It is lauded as
a "1000-hour head start" with inbuilt css and php code; everything you need to get started. We chose underscores as it
provided base structure for our code. Underscores can be found and installed here: https://underscores.me/

### Project Management

**Github**: Github is a wildly used platform for developers to build, share and maintain software, code, applications,
and more. In this project, we used Github to host a repository for all of our code and resources and to maintain
detailed version control of the changes we have made throughout
the project. Information on github can be found at https://github.com/ and this project's specific repository sits
at https://github.com/cp3402-students/cp3402-2022-1-site-team02. We use a "release" branch as our production branch and
each person editing the theme will check this out
and create their own "dev-USERNAME" branch, eventually merging to the "release" branch after testing.

**Slack**: Slack is a collaboration hub that allows team members to talk, chat, share content, plan and execute
projects, and do whatever needs to be done to get work done. It has plugins and integrations with many of the most
popular applications and services for project management, coding, design, and more.
Slack is heavily used at JCU and in the IT department specifically and was a necessity for this project. We use slack to
keep in touch with each other, plan meetings, create polls, and get a direction on our project. We used the integrations
to Github and Trello to help manage these other services from one platform. You can get started on slack
here: https://slack.com/intl/en-au/
.

**Discord**: Discord in a similar application to Slack in that it is a place to collaborate and communicate with team
members. You create servers to suit your purpose and create channels within servers to separate and organise your work.
You can chat, post images, pin messages, and store files with Discord. For this project
, Discord was used because many of the group are already a part of other Discord servers and it would have greater
visibility than slack for our purposes. You can get started with
Discord here: https://discord.com/

**Trello**: Trello is a project and team management tool designed to help teams collaborate, assign and update tasks,
and stay on track for a project. It offers an array of functions to allow
teams to update each other on task progress, comment and assist one another, and gives an overall view on the direction
a project is going. We used trello to keep organised with our tasks and goals, assign and delegate work,
and keep up to date on what each other was doing from week to week. You can get started with trello
here: https://trello.com/en. Our slack board is current public and can be browsed
here: https://trello.com/b/B4KVetgN/team-02

**OneNote**: OneNote (by microsoft) provides a sharable and editable space to write notes, lists, strategies, and other
needed documents. It creates
a living document that can be shared between team members or made public. We used OneNote specifically for our weekly
team meetings, creating task lists, checklists, and talking points as the weeks went on. You can find OneNote
here: https://www.onenote.com/download

## Environment Overview

### Local Environment

Local versions of our project (localhost) were set up identically for each team member to facilitate ease of
troubleshooting issues and to maintain
a homogeneous environment across the team. Locally, each team member worked on a Github-hosted repository using
PhpStorm, Grunt.js, and Sass. Each developer's local site was
hosted using a Bitnami Wordpress package containing the necessary database integration and apache web server. Changes
made in this local environment were pushed back to Github to synchronise with other teammates.

### Hosted Environment

Staging and Production environments are hosted using separate AWS Lightsail instances with Bitnami's Wordpress
installer. This provides a base Wordpress installation to start from and is easy for new developers to create new
instances or clone existing instances should they need to.

**Staging (development) Site**: dev.moxh.au | Changes to the overall site were done on a local instance or the dev
server, tested in dev, and eventually pushed
to production using an Import/Export plugin.

**Production (live) Site**: moxh.au

**DNS**: DNS is managed through Cloudflare (free tier) which provides a degree of separation between registrar, DNS and
hosting (AWS). Cloudflare also provides some caching capabilities in the event the site goes offline.

### Theme Development

To maintain and edit the custom theme for our site, the developers followed the below steps:

1. Checkout/pull the current 'release' branch from Github repository into a new branch (name dev-USERNAME).
2. Make required changes on dev-USERNANME branch.
3. Use preferred SSH Tool (i.e. PUTTY) and go to DEV site: `'cd stack/wordpress/wp-content/themes'`
   , `git checkout -b'dev-USERNAME'`
4. Test on DEV site to ensure changes are successful and expected.
5. If changes are successful merge dev-USERNAME branch into 'release' branch.
6. Update changes on PROD: ssh to PROD, `'cd stack/wordpress/wp-content/themes'`, `'git pull origin release'`
7. When changes have stabilized, always ensure that DEV matches the PROD site.

### Content Development

Updates to Wordpress Site Content should always be performed first in the DEV environment to avoid breaking the
PROD/LIVE site. For this project the following steps will need to be followed:

1. Make required changes to Wordpress Site/Content on Local environment (ideally) OR in DEV instance.
2. Test changes using test plan
3. Use import/export plugin to update DEV site, test again to make sure changes are not breaking PROD
4. When approved, use import/export plugin to update PROD site

### Database Considerations

During development, ensure you always have an updated copy of the production database, especially when pushing your
changes to Staging, and then Production. Pushing to Staging first ensures that both live environments have identical
content.
