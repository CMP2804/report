# Introduction
Our objective during this project was to explore non-verbal communication in singleplayer video games. Our artefact is a result of this research, taking the form of a tutorial level for a stealth game. The player character is blind and must navigate through the environment using a form of echolocation. Sources of sounds (such as moving, throwing and clapping) generate coloured points in the game world when sounds bounce off of walls, forming a simple point cloud. The artefact is comprised of two parts: the guided section and unguided section. Within the guided section, the player is introduced to the mechanics in the game and is provided with a safe environment to test these mechanics out. In the unguided section of the tutorial, the player is allowed to navigate the environment as they see fit.

# Software Engineering
## Development Metholodogy
The team considered a variety of development methodologies. A key factor in our decision was the lack of experience of the team, so the methodology we chose had to be as simple as possible. Originally, a waterfall model was considered because it is simple, linear and suitable for smaller projects like ours. However, this approach was ultimately ruled out because of large overhead costs (Sommerfield I., 2010, p.58).

Following this, agile was considered. Being well-suited to frequent changes in requirements and incremental in nature (Sommerfield I., 2010, p.59), traditional agile seemed to offer a great amount of flexibility with the project. However, with simplicity being a key factor in our decision, it was identified that changes could be made to make the metholdogy less complicated.According to Gerald Benischke (2022), Agile has a large amount of unnecessary ceremonies designed to make the methodology palatable to management. Benischke suggests that to keep Agile agile, ceremonies such as estimation, sprints & metrics should be discarded. As a team inexperienced in working in a group, it was unlikely that we would leverage these ceremonies to our advantage correctly and only serve as additional overhead, so we decided to follow Benischke's suggestions.

The resultant methodology was agile in the sense that requirements could change on-the-fly, but lacked aspects of incremental delivery and customer communication that could have informed changes to requirements that would improve the product.

## Project Structure
### Code Structure
The folder structure used in the artefact is largely defined by Unity, however the assets folder is neatly organised into a categorical list of directories for simplicity's sake.
Most are self-explanatory but there are several which are not:
- RiderFlow.UserData, ProBuilder Data & Resources: plugin data
- Prototyping: Prototyping assets
<img width="222" alt="image" src="https://github.com/CMP2804/report/assets/101411609/0d42bbcb-36e4-499a-93eb-198bda4c9f5a">


### Point Cloud Shader
In a typical Unity game, objects are rendered by the render pipeline in accordance to the materials applied to mesh surfaces. In our game however, we render the scene using a point cloud, with each point spawning on geometry when a sound is made.
In order to do this we procedurally draw sphere meshes each frame manually instead of using the standard render pipeline.
![image](https://github.com/CMP2804/report/assets/59376295/bfc7a9e9-e2a8-46a2-a6eb-b79304f843ea)

## Version Control
Git version control was used throughout the project. Being the most popular VCS of choice for developers (Stack Overflow, 2022) and having several members of the team with experience with Git, it was the obvious choice to make. We hosted our repository on GitHub for the same reasons (Stack Overflow, 2022). This migration to GitHub simplified the collaboration process and reduced the likelihood of catastrophic data loss. Whilst we used JetBrains Space for assessment 1, the migration to GitHub came with several additional features besides increased familiarity:
- Webhook support
- GitHub Desktop (for level designers and those unfamiliar with Git)
- CLI application

We decided to keep our branching strategy simple. There was one protected base branch, `submission`, from which feature branches (such as `guided_tutorial`) were branched from. Once a feature was complete, a pull request was created to merge the feature branch back into `submission` and opened to review. It is important to note that `submission` was not only protected from being pushed to directly, but also any pull requests were unable to be merged without first being approved by another member of the team. Our branching strategy is identical to the GitHub Flow (GitHub).

This lightweight workflow was simple, encouraged frequent commits and reduced the chance of merge conflicts down-the-line. Whilst the workflow was simple enough to follow in theory, in practise the team could have engaged more with pull request reviews to increase the quality of the final product.

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

Harper Section ---- Harper has made the guided tutorial section of the level which contains separate rooms for the player to move around in and different mechanics to learn. It was made using probuilder, which allows the user more freedom and tools to create levels. Using Probuilder Harper made an outline of the linear path that the player will travel through. Once done Harper reversed the Normals, which hollowed out the interior allowing for a playing area to be created. Then Harper connected the areas together, added obstacles and doors when necessary to the tutorial. These were done using the tools that Probuilder added, like the ability to have greater control of geometry through lines, vertices, and faces. Probuilder is an incredibly useful tool which allows for greater control of Geometry. Its ease of use is immediate as the controls are simple yet powerful, it gives additional functionality not offered by default Unity. This also means no external tooling is needed to create simple and complex geometry. A few challenges faced would be the initial level plan creation, and whether or not it would be suitable for the player as a tutorial. This was overcome by simplifying the initial designs and removing the unnecessary additions of geometry. The detail and complexity of the guided tutorial is low, mainly because the player will not be able to see the visual detailing due to the player only seeing with a point cloud shader. Its complexity is low as it is a tutorial section, which aims to teach the player the mechanics and game, complexity would be too much for a tutorial level. 

Jay section---- 
I designed the freeform level section of the level which contains 5 rooms and obstacles for the player to navigate and avoid enemies. The freeform level went under 2 different designs, freeform level 1 and freeform level 2. I did not have much experience with level design and the freeform level 1 turned out rather big and clunky due to all the materials and separate structures I built and jig sawed together to make the level. However, by the time I designed the second freeform level which we are using in our release, I had a bit more experience and confidence and under the guide of Harper and our project leader, Stevie, I was able to create a much more flowing, smaller, tidier level with much fewer separate structures and sort out more to do the level as I learnt more. I used pro builder for the building of the freeform level. Pro builder allows you to quickly create and prototype 3D levels, as well as create basic 3D models without leaving Unity. I made freeform level 2 by first creating a flat poly shape, an outer layer to cover the area the level was going to be and then I created another smaller floor area which was the actual size of the level, this was a plane. Then I drew a rough estimate of the rooms and floor and all the corner points and then using one poly shape I created one side of the level and using a second poly shape I created the other side of the level. I then put in all objects that the player could navigate around. I put enemies in each room and set patrol nodes, although I did run into a few problems and needed guidance from Stevie to help sort it.

## Point Cloud Rendering



### Code structure
The main two classes which manage point cloud generation are the `SoundManager` and `PointCloudRenderer` singleton classes. `SoundManager` generates the points based on physics raycasts, passing on each new point to be rendered to the `PointCloudRenderer`, which interacts with the various shaders to render each point using `Graphics.DrawMeshInstancedProcedural()`.
When and how to generate points is managed by the `SoundMaker` component, but sounds can be generated from anywhere using the static method `SoundManager.MakeSound()`.

Finding where to generate the points
In order to provide an easy in-editor way of setting up sound generation Ethan created 

![Picture1](https://github.com/CMP2804/report/assets/59376295/dd3abb5d-8ca9-421b-b950-a1809fdf10f1)

<sub>Figure 1 - Various options for changing how a sound source will transmit the sound. This example is from the player object, controlling the settings for the player's clap.</sub>

![Picture2](https://github.com/CMP2804/report/assets/59376295/c5c695cf-aef2-479f-846f-131e1072be78)

<sub>Figure 2 - A visual indicator is shown for the projection of rays which updates in real-time.</sub>

Whenever a sound is requested to be generated, `SoundManager` creates `MakerRay` structs for each ray requested randomly within the defined area. Each update a dynamic number of queued rays are processed and sent to `PointCloudRenderer` to be instanced. 
The number of rays processed each frames is determined by this calculation: `Min(200, Max(4, NumOfRaysToCast/2))`. This ensures that if the requested number of rays is too great the frame will not hand when trying to process them all, and instead the workload is spread across multiple frames. This creates the downside of the player being able to see the points generating over time instead of all at once, but this is far better than created a lag spike. A way to fully eliminate this would be to calculate the physics raycasting within a compute shader, passing the work onto the GPU to process many rays in parallel. Whilst this would solve the problem, it would require too much time to implement for the benefit it brings.

### Rendering each point
Once a point has been chosen, its information is passed to PointCloudRenderer, which holds seven parallel lists for the points data:
•	Colour – The colour of the point based on the material colour of the object hit, or the overridden colour from the ObjectHighlighter component.

•	Lifespan scale – The life in seconds of the point, used as the duration to fade the point out over.

•	Normal – The direction the point should face. This is necessary with a non-spherical mesh used for the points. Whilst the release version uses spheres for the points, we originally used quads, but decided on spheres as they looked nicer.

•	Point – The position of the point in world-space, passed directly into the shader.

•	Local point – The position of the point in local-space relative to the object the point is being created against.

•	Parent – The object the point is being created against.

•	Lifespan - The 0 to 1 current life of the point which controls the point’s alpha.

The point and lifespan data are updated each frame and aren’t set from data passed by the `SoundMaker`. The world-space point is calculated by using the `Tranform.TransformPoint()` on the local point. This effectively parents the points to whatever object they’re created from. This was done as when the player moved around, they left a trail of points, which whilst interested made it tricky to see exactly where the player was.
The lifespan value is calculated inside a compute shader, which reduces the lifespan of all points by the current delta time that frame. This is unnecessary as each point is already being iterated over each frame to delete expired points and to calculate the world-space position. A compute shader solution is implemented however as it allows more control over each point without any performance cost in the future, such as animating points or calculating physics interacts with the points.
Each frame the point material shader’s buffers are updated with the newest values for positions, normal, lifespans and colours. The material’s shader uses procedural instancing to allow multiple instances of a procedural mesh or particle system to be rendered efficiently. Within the shader the `ConfigureProcedural()` function is used to set the values of each point, with the `unity_InstanceID` used as the index of the buffers. I then do the following for setting the position of the mesh instance:
```hlsl
unity_ObjectToWorld = 0.0;
unity_ObjectToWorld._m03_m13_m23_m33 = float4(position, 1.0);
unity_ObjectToWorld._m00_m11_m22 = step;
``` 
(Flick, 2021)

This sets the fourth column of the object’s transformation matrix, which is for position. The third column is set to step, which sets the scale of the object.

In order to provide an easy in-editor way of setting up sound generation Ethan created the `SoundMaker` component which uses Odin Inspector serialisation for changing how the points are emitted and their behaviour, i.e. lifespan. This allowed us to interact with the point cloud system without needing any in-depth knowledge about how it works.
As shown in figure 1, the range and spherical sector is shown whilst the `SoundMaker` component is selected, and updates in real-time with the inspector values.
Figure 2 shows the various inspector values which can be changed, split into sections using Odin Inspector. There is a button to start and stop emission for testing purposes. 


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

Harper - I believe we have worked together well with our planning, double checking of eachothers work and file sharing all being a success. We did have issues with communication however, as it was difficult to contact/talk to another individual whom you would be working on a section with.

# References
Flick, J. (2021) Compute shaders, Catlike Coding. Available at: https://catlikecoding.com/unity/tutorials/basics/compute-shaders/ (Accessed: 09 May 2023). 
Benischke, G (2021) Less is more Agile. Available at: https://beny23.github.io/posts/my_take_on_engineering_room_9/ (Accessed: 09 May 2023)
Sommerfield, I. (2010) Software Engineering. Available at: https://engineering.futureuniversity.com/BOOKS%20FOR%20IT/Software-Engineering-9th-Edition-by-Ian-Sommerville.pdf (Accessed: 10 May 2023).
GitHub, GitHub Flow. Available at: https://docs.github.com/en/get-started/quickstart/github-flow (Accessed 10 May 2023).
Stack Overflow (2022) 2022 Developer Survey. Available at: https://survey.stackoverflow.co/2022/ (Accessed 10 May 2023).
