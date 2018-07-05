# muir-vue-template

Project template for MUIR stack including:

- muir-ml-gradle (folder marklogic)
- muir-node (folder middle-tier)
- muir-vue-ui (folder ui)

## Fetching this template

This template currently uses gitsubmodules. You can clone it recursively using:

- `git clone --recurse-submodules https://project.marklogic.com/repo/scm/\~gjosten/muir-vue-template.git {your-app-name}`
- `cd {your-app-name}`

This gives you the master branch of the template, and its submodules. Use this to get the development branch instead:

- `git clone -b development --recurse-submodules https://project.marklogic.com/repo/scm/\~gjosten/muir-vue-template.git {your-app-name}`
- `cd {your-app-name}`

It is recommended that you 'eject' from the muir code repos after cloning this template, meaning you remove the git tracking from your local copy. You can do that with:

- `rm -rf .git .gitmodules */.git`

You can then move the contents to a directory that is tracked by a different git project already, or initialize the newly created directory with a new local git repository:

- `git init`
- `git add .`
- `git commit -m "initial commit"`

In case you don't eject, you might want to occasionally check for updates, and merge them with your local setup. You can do so for all submodules using:

- `git submodule update --remote --rebase`

Or append the name of a submodule in case you like to run it for just one.

The template is still in development, so make sure to checkout dev branch in all modules:
- `git submodule foreach --recursive git checkout development`

Vue-ui requires a specific feature branch for the middle-tier as well:
- `cd middle-tier`
- `git checkout 131-search-filters`
- `cd /..`

## Getting the ui started

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

## Further reading

For more background on git submodules, see:

https://git-scm.com/book/en/v2/Git-Tools-Submodules
