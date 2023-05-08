# Software Engineering (Stevie)
The team decided to avoid prescribing to any single methodology for the project. Instead, it was suggested that the team use a combination of agile methodologies.
Taking inspiration from [this video](https://www.youtube.com/watch?v=9K20e7jlQPA) by No Boilerplate, the team used an agile methodology that avoided using ceremonies
such as sprints, stand-ups and estimation. This allowed the team to work on their tasks without unnecessary overhead, increasing productivity.
Instead, a set of tasks was created to kick off development and additional tasks were added to the backlog when needed.

## Project Structure

## Version Control
Git version control was used throughout the project.
Uploaded to GitHub, we were able to ensure that the project was available to every member of the team and work wouldn't be lost.
Using Git for version control was an obvious choice given the prevalence of Git in industry, support in IDEs and prior experience of team members.
We decided to migrate from JetBrains Space to GitHub between assessment 1 and assessment 3 because team members were more familiar with it and it has better tooling.
Some additional features of note include webhooks (for updates directly in Discord), GitHub Desktop (for members who don't use an IDE) and the CLI.
We took advantage of GitHub's pull request capabilities by using [GitHub Flow](https://docs.github.com/en/get-started/quickstart/github-flow).
This lightweight workflow is simple and encourages frequent commits and reduces the chance of merge conflicts down-the-line. We didn't have any issues applying it in the project.

## Project Planning
It was evident to the team that project planning was going to be a crucial part of working as a team. We considered various solutions, ranging from Trello to JetBrains Space.
However, it was eventually decided that GitHub was the most suitable platform to host our repository on.
As a consequence, it was only natural that we leveraged GitHub's Issues & Projects. GitHub issues offered a practical way of:
- Documenting tasks
- Describing the work that needs to be completed
- Categorizing tasks (e.g. bug, feature, documentation, etc.)
- Tracking task completion
- Assigning tasks to team members
- Discussing tasks without flooding the team group chat
GitHub Projects serves as an extension to GitHub Issues and provides the ability to create a project timeline, prioritise tasks and provide more incremental information about the state of a task.
Using these tools, we were able to create an at-a-glance Gantt chart for the project and organise the project in a clear, transparent matter.

# Implementation (various)
- Describe what has been made and how it has been made
- Justify approach taken and toolsets used
- Describe challenges faced during development & how they were overcome
- Justify detail & complexity of the project

Harper Section ----
I made the guided tutorial section of the level which contains seperate rooms for the playern to move around in and odifferent mehcanics to learn. It was amde using probuilder, which allows the user more freedom and tools to create levels. Using Probuilder i made an outline of the linear path that the player will travel through. Once done i reversed the normals, which hollowed out the interior allowing for a playing area to be created. Then i connected the areas together, added obstacles and doors when necessary to the turotial. These were done using the tools that Probuilder added, like the ability to have greater control of geometry through lines, vertices and faces. Probuilder is a highly useful tool which allows for greater control of Geometry. Its ease of use is immediate as the controls are simple yet powerful in terms of control, as it gives additional functionality not offered by default Unity. This also allows means no external tooling is needed to create simple and complex geometry. A few challenges faced would be the inital level plan creation, and whether or not it would be suitable for the player as a tutorial. This was overcome by simplifying the inital designs and removing the unnessecary additions of geometry.

Jay section---- 
I designed the freeform level section of the level which contains 5 rooms and obstacles for the player to navigate and avoid enemies. The freeform level went under 2 different designs, freeform level 1 and freeform level 2. I did not have much experience with level design and the freeform level 1 turned out rather big and clunky due to all the materials and separate structures I built and jig sawed together to make the level. However, by the time I designed the second freeform level which we are using in our release, I had a bit more experience and confidence and under the guide of Harper and our project leader, Stevie, I was able to create a much more flowing, smaller, tidier level with much fewer separate structures and sort out more to do the level as I learnt more. I used pro builder for the building of the freeform level. Pro builder allows you to quickly create and prototype 3D levels, as well as create basic 3D models without leaving Unity. I made freeform level 2 by first creating a flat poly shape, an outer layer to cover the area the level was going to be and then I created another smaller floor area which was the actual size of the level, this was a plane. Then I drew a rough estimate of the rooms and floor and all the corner points and then using one poly shape I created one side of the level and using a second poly shape I created the other side of the level. I then put in all objects that the player could navigate around. I put enemies in each room and set patrol nodes, although I did run into a few problems and needed guidance from Stevie to help sort it.

# Testing Strategy (Stevie)
- Detail the testing strategy the team used & how it was implemented
    - Unit tests
    - User acceptance tests
    - Mandatory code reviews
- Provide evidence of testing
- List sample tests
- Discuss how issues were approached
A key issue that was identified early on in development was the need for a testing strategy to validate our work. To address this, Stevie came up with a comprehensive yet lightweight testing strategy that didn't require a lot of overhead.

## Unit Tests
Stevie identified that GitHub Actions could be used to create an automated testing system for developer-defined unit tests. These tests were set up to run every time a member of the team pushed to GitHub or created a pull request. This provided the team with confidence that existing systems remained functional without having to extensively test the entire program manually. Stevie identified [game.ci](https://game.ci) as a resource that provided helpful GitHub Action workflows to automate Unity engine testing on GitHub.
Once set up, few issues were encountered. However, the player movement test cases seemed to fail randomly and without reason. We believed it was associated with inaccuracies associated with float point arithmetic, so Ethan adjusted the test cases to be approximate, which solved the issue.
<img width="800" alt="image" src="https://user-images.githubusercontent.com/101411609/236839679-c94798c3-893a-4c48-b63f-0ac38ed86f35.png">
<img width="800" alt="image" src="https://user-images.githubusercontent.com/101411609/236840127-b7d50ea7-2388-4c51-b6a8-40e42389dd9a.png">
<img width="677" alt="image" src="https://user-images.githubusercontent.com/101411609/236840837-09a82517-1c34-4c46-9444-bd46540945cd.png">

## User Acceptance Tests
Two weeks before release, we ran a set of user acceptance tests using a small set of playtesters. There were plans for a more extensive playtesting session, however only Stevie was able to successfully acquire playtesters, limiting the amount of feedback recieved. These were performed over Discord video calls and consisted with players proceeding through the tutorial level, commenting on any confusion they had. For example, one playtester commented that often walls were difficult to spot and it was not immediately obvious if short walls were able to be passed through or not. 
A multitude of areas for improvement were identified through this process and these were added to the backlog of tasks. However, a small amount remained unaddressed as the team was focused on completing other assignments. In the future, this process could have been improved by incorporating evaluation such as heuristic, quantitive and qualititve evaluation.

## Code Reviews
According to our branching strategy, features must be created and merged into the `submission` branch using a pull request. A branch protection rule was created for the submission branch that not only prevents pushes directly to `submission`, but also prevents the merging of pull requests without first being approved by another member of the team. This allowed the team to verify the team to validate one another's solutions by looking at the work from another perspective. However, more often than not, this review process was bypassed using administrator privileges. In the future, this process could be improved by encouraging other members of the team to engage in collaborative code reviews.

# Release (Jay?)
- Discuss how the artefact was released
- Explain choice of platform used for release
- Describe how issues on release were addressed
- Provide link to GitHub repository & platform used for distribution

We’ve selected Itch.io as the platform for releasing our game and a few of the reasons for choosing Itch.io being: Itch.io describes itself as “an open marketplace for independent digital creators with a focus on independent video games”. Functionally speaking Itch.io gives developers complete creative freedom over anything they create. They're able to set the price, choose the timing and form of their sales, and heavily customize their product page and there's no cost tied to any of this. Itch.io also supports pre-orders, selling rewards, creating early-access content, bundling your content, and even doing crowdfunding with project goals. The creator dashboard on Itch.io gives easy access to data about what uploads resonate the most or what links drive the most attention. Itch.io is also largely accessible on a multitude of platform devices. The public will also be able to play the game without having to download any files.  

That means by releasing our game on Itch.io as part of a release plan, we could release a beta version to the public for free and generate feedback from public players as too improvements and what people would like to pay for a full release this would also give us a good idea if there would be any problems on release but it’s impossible to foresee everything. We could then take the product and sort out any release issues, improvements and any bugs and then re-release it as an alpha test for the next part of the release plan. If problems or improvements continued to occur, we could just repeat this phase of the plan until it was fully ready for release and then release it as a full game and then deal with any problems as they occurred upon release.

https://github.com/CMP2804/Assessment3/releases/tag/Release



# Evaluation (Stevie & Jack?)
- Discuss how the project went & what could have been improved
- Document user reviews of the artefact
- Discuss how the artefact could be developed further in the future

# Media Materials (Ryan?)
- Create & link a 2-minute video used for marketing
- Create other marketing materials

# Group Work Reflection (various)
- Detail how the team has worked together
- Cover successes and issues that have been encountered
- Include individual contributions table
