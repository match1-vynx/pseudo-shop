# Final Project Retrospective

## Team Members
- Student 1: Michelle Tolentino
- Student 2: Rafael Sebastian Torres
- Student 3: Gabriel Naoe

## 1. How did you divide the work between you and your partner?
_(Who worked on which features? How was the work assigned or negotiated?)_

We divided the work by first identifying which features could be developed independently and which features had dependencies on shared files or shared data structures. Instead of having everyone work directly on the same files at the same time, we followed a feature-based development workflow similar to how software teams avoid pushing unfinished changes directly to production.

In our project, we treated the `main` branch as the stable production-like branch. Because of this, each member worked on a separate feature branch first. This allowed us to isolate changes, reduce unnecessary conflicts, and review the behavior of each feature before integration.

### Work Assignment

After discussing the requirements, we agreed on the following division of work:

| Member | Assigned Feature | Responsibility |
|---|---|---|
| Rafael | Feature 1: Filter Products by Attributes | Implemented product filtering based on product attributes such as width, height, length, weight, color, and brand |
| Michelle | Feature 2: User Registration and Login | Implemented user account creation, login validation, and in-memory user storage |
| Gab | Feature 4: Display Storefront | Implemented storefront display logic for rendering product information |
| Michelle | Feature 3: Product Creation and Listing | Implemented product creation after the product model and display logic were established |

### Coordination and Dependencies

Although each member had an assigned feature, we still had to coordinate because some features depended on the same product data structure. Specifically, **Feature 1** and **Feature 4** both relied on the `Product` model. Rafael and Gab coordinated on the expected product attributes so that the filtering logic and display logic would use the same structure consistently.

We recognized that **Feature 3: Product Creation and Listing** depended on the product model being stable first. Since product creation needed to instantiate products and append them to `product_list`, we decided to implement it after the filtering and storefront display features had clarified the required product fields. This helped avoid redesigning the product model multiple times.

### Integration Strategy

For integration, we first merged Rafael’s filtering work and Gab’s storefront display work, since both were closely related to the product model. After that, we checked the combined version for merge conflicts, naming inconsistencies, and mismatched product attributes.

Once Features 1 and 4 were integrated, Michelle used that merged version as the base for Feature 3. This was similar to creating an integration layer where related changes are combined and tested before being merged into the stable branch.

Finally, we reviewed the completed branches before merging them into `main`. Since Michelle owned the GitHub repository, the final merge into `main` was done through her account.



## 2. What Git strategies or commands helped you most during the project?
_(E.g., branching, rebasing, frequent commits, etc.)_

The Git strategies that helped us most were creating feature branches for each task, making frequent commits with clear messages, and pulling updates regularly before continuing work. Branching allowed us to work separately without disrupting the main project, while consistent commits made it easier to track changes and review progress. 

We also found that communicating before merging helped prevent unnecessary conflicts and kept the workflow organized. These habits made collaboration smoother and more reliable throughout the project.


## 3. Describe a merge conflict you encountered. What caused it and how did you resolve it?
_(Include any lessons learned or techniques used to resolve the issue.)_

The merge conflict happend while trying to combine features 1 and 4. Rafael was working on a product filtering feature and at the same time, Gabriel was on a separate branch developing the storefront display feature. They were both editing the same core repository file but did not touched each other's code. However they both appended their functions to the very bottom of that file (store_view).

After this, a branch `feat/product-management` was created to combine our work since they used the same files. First, the product filtering branch was successfully merged into `feat/product-management` beecause it was the first piece of code going into the new branch, the merge went through smoothly without any issues.

The conflict happened right after, when Rafael tried to merge the `feat/display-storefront` to bring in Gabriel's work. Git immediately halted the merge process in my terminal and flagged a conflict error.

Because we both had appended our new functions to the very bottom of that same file, Rafael's filtering function now occupied the exact same line numbers where Gabriel’s storefront function was trying to sit. Git couldn't automatically determine how to order them.

To resolve it, Rafael opened the file in an editor and found Git's conflict markers separating the filtering function from Gabriel's storefront code. He manually deleted the markers, stacked the functions so both features could coexist, and saved the file. Finally, he ran added and committed the resolution, successfully finalizing the merge on our `feat/product-management` branch.


## 4. What were the biggest challenges you faced as a team?
_(This can include communication, Git usage, or coordination.)_

One of the biggest challenges we faced at the beginning was understanding the scope and dependencies of each feature. Although the features were listed separately, some of them still depended on shared files, shared functions, or common data structures. 

To address this, we discussed the expected behavior of each feature and clarified the required product attributes before continuing with implementation. Once we agreed on the feature specifications and the shared structure of the product model, it became easier to develop each feature independently while still keeping the overall system consistent.

In terms of version control, working with feature branches was relatively manageable because most of the features were moderately isolated. Since we communicated the expected product fields and function responsibilities early, our merge conflicts were easier to understand and resolve. This helped us avoid unnecessary overwriting of each other’s work.

We also encountered a minor issue where some file changes did not appear immediately after pull requests or merges. This seemed to be related to the IDE not refreshing or updating the local files automatically. We resolved this by restarting the IDE and rechecking the repository state using Git commands.


## 5. What did you learn about using Git in a collaborative setting?
_(Any insights or habits you’d apply in future projects?)_

- **Michelle** - I learned that Git is not only a tool for saving code changes, but also a workflow for coordinating development across a team. Using feature branches helped us isolate work, protect the `main` branch, and integrate changes more intentionally. I also learned the importance of understanding dependencies between features before merging, especially when multiple members are working with shared files or shared data structures.

- **Rafael** - I discovered that following a consistent branching strategy helps teams avoid unnecessary conflicts and maintain a smoother workflow. By working on separate branches for individual features or fixes, we were able to develop independently without interfering with each other’s progress. This also made merging changes more organized and reduced the likelihood of complex merge conflicts.

- **Gab** - I learned that regular and descriptive commits are important to prevent confusion and keep the project organized, especially when using Git collaboratively. I also learned that branching is useful for working on features separately without disrupting the stable version of the project.

---

## 6. How would you improve your workflow next time?
_(Think about technical habits and teamwork practices.)_

- **Michelle** - Next time, I would establish a more formal review process using pull requests instead of relying only on direct branch merges. Pull requests would make it easier to review changes, discuss implementation details, and verify that the feature is ready before merging it into the stable branch. This would better simulate real software engineering workflows where changes are reviewed before being integrated.

- **Rafael** - Next time, I would create smaller and more focused commits so that each commit represents a clear and specific change. I would also merge or pull updates from the main branch more often to keep my feature branch updated and reduce the risk of larger conflicts later.

- **Gab** - Next time, I would review the code more carefully before merging changes into the main branch. I would also maintain a simple task checklist to track which parts of the feature have been completed, what still needs improvement, and whether the feature meets the exit criteria before integration.

---

## 7. Optional: Any feedback on the activity?
_(What worked well? What was confusing or could be improved?)_

- **Michelle** - I liked how the activity represented the collaborative nature of Git through group work, branching, merging, and conflict resolution. The mini-capstone format was also engaging because it allowed us to apply Git concepts in a more realistic project scenario.

- **Rafael** - I liked the activity because I was able to use Git in a way that is similar to how it would be used in a real-world development environment. It helped me better understand the importance of branches, commits, and controlled merging.

- **Gab** - The activity was a useful way to practice teamwork and Git in a realistic setting. It helped me understand how branching, commits, and conflict resolution work together in a collaborative project.