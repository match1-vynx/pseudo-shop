# Final Project Retrospective

## Team Members
- Student 1:
- Student 2:

## 1. How did you divide the work between you and your partner?
_(Who worked on which features? How was the work assigned or negotiated?)_
mich

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
mich

## 5. What did you learn about using Git in a collaborative setting?
_(Any insights or habits you’d apply in future projects?)_
all

rafael
I discovered that following a consistent branching strategy helps teams avoid unnecessary conflicts and maintain a smoother workflow. By working on separate branches for individual features or fixes, we were able to develop independently without interfering with each other's progress. This also makes merging changes more organized and reduces the likelihood of complex merge conflicts.

gab 
I learned that regular and descriptive commit is important to prevent confusion and keep the project organized especially when using Git. I also learned that branching is very useful for working on features separately without disrupting the main work.

## 6. How would you improve your workflow next time?
_(Think about technical habits and teamwork practices.)_
all

rafael 
I would create smaller, focused commits and merge updates into my branch more often to reduce the risk of conflicts.


gab
I would test or review the code more carefully before merging changes into the main branch. I would keep a simple task checklist to track what has been completed and what still needs work.
## 7. Optional: Any feedback on the activity?
_(What worked well? What was confusing or could be improved?)_
all

rafael 
I liked the activity as I was able to use Git similar to how it would be used in a real-world environment. 

gab
The activity was a useful way to practice teamwork and Git in a realistic setting. It helped me understand how branching, commits, and conflict resolution work together in a collaborative project.