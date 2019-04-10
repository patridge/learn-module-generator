# yo learn-module - Microsoft Learn content templates

This is the repo for documentation about the Microsoft Learn template system available on [npm](https://npmjs.com/package/generator-learn-module). It is also a great location to [make feature requests or file bugs](https://github.com/patridge/learn-module-generator-public/issues).

These templates are intended for Microsoft employees writing content for [Microsoft Learn](https://aka.ms/learn). Each template is designed to streamline the creation of various Microsoft Learn content pieces, which often contain several metadata and configuration elements expecting very specific values.

## Installation

Run the following command to install both the [learn-module generator](https://www.npmjs.com/package/generator-learn-module) and the prerequisite [Yeoman](http://yeoman.io/) to make them available everywhere on your computer:

```bash
npm install -g yo generator-learn-module
```

> NOTE: To run any Yeoman generators, you need to have npm installed, which is included with Node.js.
> To [install Node.js](https://nodejs.org/en/download/), download the run the latest LTS release for your operating system.
> With Node.js installed, run the following command to install the latest npm for managing Node.js packages.
>
> ```bash
> npm install npm@latest -g .
> ```

## Available templates

* [Module](#Generate-a-module)
* [Unit](#Generate-a-module-unit)
* [Knowledge check](#Generate-a-module-knowledge-check)

## Run `yo learn-module`

The learn-module generator will walk you through the steps required to create various Microsoft Learn content. The first question will ask what type of content you wish to create. This decides what questions you will be asked to populate the new files it will generate.

To launch the generator simply type:

```bash
yo learn-module
```

> NOTE: If you answer a question incorrectly, you can either cancel the Yeoman generator entirely using <kbd>Ctrl</kbd>-<kbd>C</kbd> and run it again or fix the incorrect information in the resulting files.

### Generate a module

To start a new Learn module, run `yo learn-module` and pick the **New module** template from the first question.

Alternatively, you can pre-pick this template by providing the template value from the command line.

```bash
yo learn-module --template="module"
```

This template will create a base folder structure of YAML and Markdown content, with the `{your-module-id}` value automatically derived from the module title you provide.

* ./{your-module-id}/
  * index.yml
  * 1-introduction.yml
  * 6-summary.yml
  * /includes/
    * 1-introduction.md
    * 6-summary.md

While you will want a module summary, do not feel obliged to keep it as the sixth unit in your module. Just remember to renumber the YAML and Markdown files as well as the ID in the index.yml and the 6-summary.yml files.

### Generate a module unit

To add a unit to an existing Learn module, make sure you are currently working from the module folder in your command line terminal and run `yo learn-module`; pick the **Module unit (YAML+Markdown)** template from the first question.

Alternatively, you can pre-pick this template by providing the template value from the command line.

```bash
yo learn-module --template="module-unit"
```

This template will create a unit YAML metadata file and Markdown content file with the `{step-number}-{unit-title-id}` value automatically derived from the step number and unit title values you provide.

* ./{step-number}-{unit-title-id}.yml
* ./includes/{step-number}-{unit-title-id}.md

You will still need to add your unit's ID to the current module's **index.yml** file manually to the `units` list.

### Generate a module knowledge check

To add a knowledge check unit to an existing Learn module, make sure you are currently working from the module folder in your command line terminal and run `yo learn-module`; pick the **Module knowledge check (YAML)** template from the first question.

Alternatively, you can pre-pick this template by providing the template value from the command line.

```bash
yo learn-module --template="module-knowledge-check"
```

This template will walk you through creating a knowledge check unit YAML file (metadata and quiz question data).

* ./{step-number}-knowledge-check.yml

You will still need to add your unit's ID to the current module's **index.yml** file manually to the `units` list.

## History

* 1.7
  * Add knowledge check template (previously a separate repo).
  * 1.7.2
    * Remember user input for GitHub and Microsoft usernames.
  * 1.7.3
    * [module] Fix missing UID periods and lost module questions.
  * 1.7.4
    * [knowledge-check] Add missing YAML value quotes.
  * 1.7.5
    * ([#32](https://github.com/patridge/learn-module-generator/issues/32)) Fixed duplicate repo portion of predicted module ID.
    * Lots of internal improvements to code organization and de-duplication.
* 1.6
  * Fix ID bug with titles containing " - " (e.g., "Exercise - Do something awesome"). [Thanks for reporting @jasallen.]
  * [Unit] Fix: use provided title (no more "Introduction" units). [Thanks for reporting @jasallen.]
  * Change template names internally and user-facing prompt copy to be more descriptive.
  * [dev] Add first unit tests via Mocha (as a dev dependency).
* 1.5
  * Added content file template to create an arbitrary unit (#-unit-name.yml and includes/#-unit-name.md)
  * Added initial template selection question to decide between multiple templates (currently two)
* 1.4
  * Added repo suffix prompt
  * Added command-line argument support
  * Removed some legacy items
* 1.3
  * Updated to new module badge YAML schema.
  * 1.3.1
    * [dev] Added VS Code debug support for macOS and Windows with global Yeoman install
* 1.2
  * Added new sub-products.
* 0.1
  * Generates the basic scaffolding for a new Microsoft Learn module.

## License

[MIT](https://github.com/patridge/learn-module-generator/blob/master/LICENSE)
