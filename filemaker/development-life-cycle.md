# FileMaker Development Life Cycle

**Draft**

All FileMaker features should go through the following general process.

### 1. A detailed story is written by the PM.
The story should target the smallets possible set of new/updated features. Related feature changes should ideally be broken out into separate stories if possible in order to minimize the complexity of development and testing.

### 2. The story is reviewed and scored by the FileMaker team.
The FileMaker team reviews the story. They may as for clarrifications or bring up missed details. If the story is found to cover too many disparate changes/additions then the team may ask for the story to be broken down into separate stories. Assuming the story is understood and needs no changes, then the team will proceed to score the story based on complexity. This part of the process ideally occurs druing a short weekly Backlog Grooming meeting.

### 3. The story gets prioritized by the PM.
Once the story has been scored, then the PM should prioritize the story against other FileMaker stories. This should be done by assigning a due date and updating the due dates of other stories if needed.

### 4. The story gets developed by a FIleMaker developer.
If the story was not specifically assigned to a developer, then a developer who has no pending-assigned stories should claim it. The story should then be developed. If an existing solution is being modified then a new version of the solution should be created as detailed in the [Solution Version Management](solution-version-management.md) documentation. Before completion of development the [Definition of Done](definition-of-done.md) should be reviewed. Once the DoD is passing, then the story can be sent to a second FileMaker developer for review.

### 5. The solution is reviewed by a second FileMaker developer.
The solution should be demoed for and reviewed by a second FileMaker developer. See the [Solution Review](solution-review.md) documentation for details. Any issues found will move the story back to step 4 of the process. Upon completion of review the solution can be deployed for testing by QA and the PM.

### 6a. The solution gets tested by the QA team.
A QA team member will test the solution based on the requirements of the story and their understanding of the larger system. They will specifically test the feature requirements as well as do exploratory and regression testing of the systems that touch the new/updated solution. Any issues found will move the story back to step 4 of the process.

### 6b. The solution gets reviewed by the PM.
The PM will review and test the solution. Any problems found with the implementation of the feature requirements will result in the story going back to step 4 of the process.

### 7. Release of the solution.
Once QA and the PM have signed off on the solution it can be released. See the [Release Process](release-process.md) for details.