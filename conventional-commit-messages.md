[Index](https://github.com/astrekhin/bash-git-vim-notes)

# Conventional Commit Messages 

```bash
git commit -m <message>                   # basic
git commit -m <title> -m <description>    # detailed
```

## Commit Formats (Формат коммитов)

### Default (По-умолчанию)
<pre>
<b><a href="#types">&lt;type&gt;</a></b></font>(<b><a href="#scopes">&lt;optional scope&gt;</a></b>): <b><a href="#subject">&lt;subject&gt;</a></b>
<sub>empty separator line</sub>
<b><a href="#body">&lt;optional body&gt;</a></b>
<sub>empty separator line</sub>
<b><a href="#footer">&lt;optional footer&gt;</a></b>
</pre>

### Merge (Слияние)
<pre>
Merge branch '<b>&lt;branch name&gt;</b>'
</pre>
<sup>Follows default git merge message</sup>


### Types (Типы)
* API relevant changes
    * `feat` Commits, that adds a new feature (добавление новой функциональности, соотносится с `MINOR`)
    * `fix` Commits, that fixes a bug (исправление ошибок в коде, соотносится с `PATCH`)
* `refactor` Commits, that rewrite/restructure your code, however does not change any behaviour
    * `perf` Commits are special `refactor` commits, that improve performance
* `style` Commits, that do not affect the meaning (white-space, formatting, missing semi-colons, etc)
* `test` Commits, that add missing tests or correcting existing tests (добавление или корректировка тестов)
* `docs` Commits, that affect documentation only (обновление документации, например, README.md)
* `build` Commits, that affect build components like build tool, ci pipeline, dependencies, project version, ... (сборка)
* `ops` Commits, that affect operational components like infrastructure, deployment, backup, recovery, ...
* `chore` Miscellaneous commits e.g. modifying `.gitignore`

### Scopes (Область)
The `scope` provides additional contextual information.
* Is an **optional** part of the format
* Allowed Scopes depends on the specific project
* Don't use issue identifiers as scopes

### Subject (Краткое описание)
The `subject` contains a succinct description of the change.
* Is a **mandatory** part of the format
* Use the imperative, present tense: "change" not "changed" nor "changes"
* Don't capitalize the first letter
* No dot (.) at the end

### Body (Тело)
The `body` should include the motivation for the change and contrast this with previous behavior.
* Is an **optional** part of the format
* Use the imperative, present tense: "change" not "changed" nor "changes"
* This is the place to mention issue identifiers and their relations

### Footer (Подвал)
The `footer` should contain any information about **Breaking Changes** and is also the place to **reference Issues** that this commit refers to (соотносится с `MAJOR`).
* Is an **optional** part of the format
* **optionally** reference an issue by its id.
* **Breaking Changes** should start with the word `BREAKING CHANGES:` followed by space or two newlines. The rest of the commit message is then used for this. 


### Examples (Примеры)

#### feat - добавление новой функциональности

* ```
  feat(lang): add russian language
  ```
* ```
  feat(parser): add ability to parse arrays
  ```
* ```
  feat(shopping cart): add the amazing button
  ```
* ```
  feat: remove ticket list endpoint
  
  refers to JIRA-1337
  BREAKING CHANGES: ticket enpoints no longer supports list all entites.
  ```

#### fix - исправление ошибок в функциональности

* ```
  fix: add missing parameter to service call
  
  The error occurred because of <reasons>.
  ```
* ```
  fix: minor typos in code

  see the issue for details on the typos fixed

  fixes issue #12
  ```
  
#### docs - добавление или изменение документации

* ```
  docs(MockConnections): add mockError usage example
  ```
* ```
  docs: correct spelling of CHANGELOG
  ```
* ```
  docs(zone.js): update DEVELOPER.md for changelog instruction (#32016)
  ```
* ```
  docs: improve README.md
  ```
#### test -  добавление тестов (unit tests)

#### refactor - изменение кода без добавления функциональности или исправления ошибок (удаление избыточного кода, переименование переменных)

* ```
  refactor(aio): remove redundant styles
  ```
* ```
  refactor(compiler): rename decorator directives into directive
  ```
 
#### perf - улучшение производительности

* ```
  perf(payments): improve payment processing by 500ms
  ```

#### chore - без особого смысла

* ```
  chore: Fix XAML parsing sample
  ```
* ```
  chore: move rock.mp3 into music
  ```
  
#### build - сборка версий, библиотек, зависимостей (некоторые пишут в chore)
  
* ```
  build(release): bump version to 1.0.0
  ```
* ```
  build: release version 2.1.0
  ```
* ```
  build: update dependencies
  ```

#### style - изменение стиля, не влияющего на код (отсутствие запятой, точки с запятой, пробела)

* ```
  style: remove empty line
  ```
* ```
  style(playground): use single quotes consistently
  ```
* ```
  style(aio): add space between `.home` and `.hamburger`
  ```
* ```
  style(nodeTree): fix formatting
  ```


---
  
### Sources (Источники): 
1. [Conventional Commit Messages](https://gist.github.com/qoomon/5dfcdf8eec66a051ecd85625518cfd13)
2. [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
