Branch Protection Rules Justification
To maintain code quality, stability, and team collaboration, we have enabled branch protection rules on the main branch. These rules ensure that only tested and reviewed code is merged into production-level code.

 Active Rules on main Branch
Require Pull Request Reviews

At least one team member must review all code before it can be merged.

This helps catch bugs early and promotes collaborative development.

Require Status Checks to Pass

All GitHub Actions workflows (e.g., CI tests) must complete successfully before a pull request is merged.

Prevents unstable or broken code from entering the main codebase.

Disable Direct Pushes

Developers cannot push directly to main. All changes must come via pull requests.

Guarantees all code changes are reviewed and tested.

 Benefits
Improved Code Quality: Every change is peer-reviewed and tested before merging.

Safer Releases: Prevents untested or broken code from reaching users.

Better Collaboration: Encourages discussion and review of changes via pull requests.

Compliance and Audit Trail: Every change is traceable with commit history and reviews.

Example Workflow
Developer creates a new feature branch.

Pushes code and opens a pull request to main.

CI/CD pipeline automatically runs all tests.

If tests pass and PR is approved, it can be merged.

On merge, a release artifact is automatically generated.


