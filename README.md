# Cypress automation Visual test

Tools :  
- cypress
- cypress-image-snapshot
- Cypress Image Diff HTML Report
- typescript

## Getting Started

To run `cypress-automation` locally:

1. Make sure you already installed NODE v14.16.1 or higher and yarn package before installing Cypress
2. Clone this repo
3. Change directory: `cd visual_test_cypress`
4. Install dependencies: `yarn` or 'npm'

## Docs to help on 
- https://cypress.visual-image-diff.dev/getting-started 


## Notes for Developers / AQAS / QAs
### How to run the tests locally

1. To run in Mode Gui ` npm run cy:open `
  1.1 and the mode gui will open 
  2.2 select the E2E testing
  1.3 Select Start E2E test 
  1.4 select the spec and click in the link 
  1.5 so the test will start to run 
2. if you want to run in mode non-gui run the command line `npm run cy:run`
3. run the command line `npm run view-test` to see the report locally , 
   3.1 the server will run and you will see the message like that  `🚀 Server running on http://127.0.0.1:6868`

### Commands

`cypress-image-diff -u ` - Notice that you should run this command after the test suite runs. The below command will only update baseline images that have a diff image, which basically means a test failure.

`cypress-image-diff-html-report start `: to serve the HTML report out of a generated JSON file in an interactive mode, where you can update the baseline screenshots.

`cypress-image-diff-html-report generate `: to generate and write to disc the HTML report in case you just want to view the static report.

` Updating baseline images`  - you can delete the baseline image cypress-image-diff-screenshots > baseline ,
that you wish to be updated and rerun the tests by running the `npm run cy:open`,
this will create a new baseline image with the updated image.

### CLI 

0. Generate the environment global $**CI_REPORTS_DIR_**
1. Verify if the cypress-image-diff-js was installed and exist  - `_ls -la node_modules/cypress-image-diff-js/dist/_`
2. Verify if was generated report and images - `_ls -la $CI_REPORTS_DIR_`
3. Verify if exists the Baseline Images folder - `_ls -la cypress-image-diff-screenshots/baseline/_`
4. Verify if exists the Comparison Images folder - `_ls -la cypress-image-diff-screenshots/comparison/_`
5. Verify if exists the Diff Images folde - `_ls -la cypress-image-diff-screenshots/diff/_`
6. Generate Visual Test Report -` _./node_modules/.bin/cypress-image-diff-html-report generate --rd=$CI_REPORTS_DIR_`
7. Copy all the report and images folder on the gitlab pages  
