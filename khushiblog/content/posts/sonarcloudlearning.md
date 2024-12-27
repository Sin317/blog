---
title: 'Sonarcloudlearning'
date: 2024-10-09T23:17:55-07:00
draft: false
# weight: 1 # for pinning
# aliases: ["/first"]
tags: ["sonarcloud"]
author: "Khushi"
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "My exploration and debugging in sonarcloud"
canonicalURL: "https://canonical.url/to/page"
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "<image path/url>" 
    alt: "<alt text>" 
    caption: "<text>" 
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/sin317.github.io/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---
Sonarcloud:
Useful to get static code analysis.

Configuration with Azure Pipelines:

```
# Prepare SonarQube analysis configuration.
- task: SonarQubePrepare@3
  inputs:
    SonarQube: # string. 
    scannerMode: 'MSBuild'
    cliProjectKey: # string. Required when scannerMode = CLI && configMode = manual. Project Key. 
    projectKey: # string.

```

Guidelines:
1. Ensure to use version 3 and above. Previous ones are deprecated and will not be able to find the generated test analysis files.
2. If the code and tests are under the same src folder, then write the files that need to be excluded in the .xml file:
```
<ItemGroup>
    <TestProjects Include="src/Tests/**/*.csproj" />
</ItemGroup>
```
