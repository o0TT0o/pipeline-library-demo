# pipeline-library-demo

Demonstrates how to use a Shared Library in Jenkins pipelines. This repository defines a single function, `sayHello`, which will echo a greeting.

## Setup instructions

1. In Jenkins, go to Manage Jenkins &rarr; Configure System. Under _Global Pipeline Libraries_, add a library with the following settings:

    - Name: `pipeline-library-demo`
    - Default version: Specify a Git reference (branch or commit SHA), e.g. `master`
    - Retrieval method: _Modern SCM_
    - Select the _Git_ type
    - Project repository: `https://github.com/monodot/pipeline-library-demo.git`
    - Credentials: (leave blank)

2. Then create a Jenkins job with the following pipeline (note that the underscore `_` is not a typo):

    ```
    @Library('pipeline-library-demo')_

    stage('Demo') {

      echo 'Hello World'
   
      sayHello 'Dave'

    }
    ```

This will output the following from the build:

```
[Pipeline] stage
[Pipeline] { (Demo)
[Pipeline] echo
Hello world
[Pipeline] echo
Hello, Dave.
[Pipeline] }
[Pipeline] // stage
[Pipeline] End of Pipeline
Finished: SUCCESS
```
# Lion
## TODO List
### docker
[x] withdocker
[x] docker build
[x] docker push

### input
[x] parameters
[x] input request

### cache
[ ] stash
[ ] mount

### kubernetes
[ ] deploy
 
### cloud
[ ] aws-ci
[ ] terrform

### flow
[ ] define
[ ] switch
[ ] nested

### notify
[ ] mail
[ ] slack

### deployment
[ ] bludgreen
[ ] canary

### build
[ ] compile
[ ] package
[ ] upload
[ ] scan

### common
[ ] discard
[ ] clean WS
[ ] agent
[ ] parallel
[ ] when
[ ] options
[ ] environment
[ ] timeout
[ ] credentials
[ ] declarative
[ ] scripted

### trigger
[ ] cron
[ ] pollscm
[ ] upstream
[ ] when

### martix
https://www.jenkins.io/doc/book/pipeline/syntax/

### unit test
https://www.jenkins.io/doc/book/pipeline/development/#unit-test

### [x]lint
https://www.youtube.com/watch?v=aFRjn_4nb-Q&list=PLKaiHc24qCTSnXaus2t4b71ihq9k649XS
https://www.jenkins.io/doc/book/pipeline/development/#visualstudio-code-jenkins-pipeline-linter-connector
