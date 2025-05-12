
---

### 🔄 How the CI/CD Pipeline Works

```markdown
## CI/CD Pipeline Overview

This project uses GitHub Actions for continuous integration and deployment.

- On every **push** and **pull request**, the `ci.yml` workflow runs:
  - Sets up the Java environment.
  - Runs all unit and integration tests.
  - Blocks merges to `main` if tests fail.

- On **merge to `main`**, it:
  - Builds the JAR file using Maven.
  - Uploads the JAR as a GitHub Actions artifact.

You can find the workflow in `.github/workflows/ci.yml`.

