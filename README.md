# git-hooks-nodejs-template
NodeJS application with Husky and Commitlint

Testing, linting and verification of the commit message using automated Git Hooks with help of Husky, Commitlint and lint-staged NPM packages

Enter  `npm install` after cloning to make use of all hooks

### The Hooks in this template
1. pre-commit: 
    - All testing file under tests folder need to pass for success commit. If you want to add extra test file, simply add the file under tests folder, and name it with the format <tested filename>.test.js
    - All file in src folder need to match the syntax rules of **eslint**
    - As we are using lint-staged, only file in staging area will be tested 
2. commit message
    - All commit message need started with [ISSUE-]
    - Example commit message: *"[ISSUE-12] Added commitlint"*
    - To modify the rules, go to **package.json** file, under **commitlint** -> **parserPreset** -> **parserOpts** -> **issuePrefixes**, change the prefix rules
3. post commit  
    - Simply echo "Thanks for committing $GIT_AUTHOR_NAME" message if commit success
    - To modify the message, go to **package.json** file, under **scripts** -> **success-message**, modify the success messages
  
### Note for Window user
If you are facing the issue of **1:16  error  Expected linebreaks to be 'LF' but found 'CRLF'  linebreak-style**, That is because in window the linebreaks will be replaced to CRLF when commiting. Simply run `npm run lint-fix` and commit again.
