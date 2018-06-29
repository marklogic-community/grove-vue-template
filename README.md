# muir-vue-template

Project template for MUIR stack including:

- muir-ml-gradle (folder marklogic)
- muir-node (folder middle-tier)
- muir-vue-ui (folder ui)

## Getting started

This template currently uses gitsubmodules. You can clone it recursively using:

- `git clone --recurse-submodules https://project.marklogic.com/repo/scm/\~gjosten/muir-vue-template.git {your-app-name}`
- `cd {your-app-name}`
- `rm -rf .git .gitmodules */.git`

After that, consider adding everything as initial commit to a new git repo.

Quick steps to get the default vue app up and running:

- `cd marklogic`
- `echo "mlAppName=my-fancy-app" > gradle.local.properties`
- Override host, port, user, pass as needed in there as well
- `./gradlew mlDeploy loadSampleData`

- `cd ../middle-tier`
- `echo "MUIR_APP_NAME=my-fancy-app" > .env.local`
- `npm install`
- `npm start` (keep open)

- Open a new terminal window
- `cd ../ui`
- `npm install`
- `npm run serve`
- A browser window should open automatically (at localhost:8080)

Look inside the subfolder README's for more detailed instructions.
