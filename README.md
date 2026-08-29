
# Micro Site CI/CD Pipeline

## Repository Structure

```text
├── .github/workflows/deploy.yml  # GitHub Actions CI/CD Pipeline configuration
├── index.html                    # Main page
└── package.json                  # Node.js project dependencies
```

## CI/CD Pipeline Flow 

1. **Validation Phase:** Triggered automatically on all Pull Requests and direct Pushes to `main`.
   * Checks out the codebase.
   * Sets up a Node.js runtime environment.
   * Runs `npm run lint` scan code structures.
   * Runs `npm test`  run test
   * Runs `npm run format:check` Check format 
   * Runs `npm test` Run define tests 
   * Builds the site into a directory (`/dist`).

2. **Deployment Phase:** Triggered ONLY on direct merges or pushes to the `main` branch.
   * Publishes the contents of the `/dist` directory to github page

3. **Deployment Approval**
   * Go to Repo settings 
   * Click on Environment and select `github-pages` environment 
   * Check on `Required reviewers` Add Required reviewers for deploymnet and Save
## Local Development & Testing

* Download and install all the dependencies listed in your package.json
  ```bash
  npm install
  ```
* **Verify Code Quality :**
  ```bash
  npm run lint
  ```
* **Execute Test Cases:**
  ```bash
  npm test
  ```
* **Compile Project Assets:**
  ```bash
  npm run build
  ```