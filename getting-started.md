# Getting Started

## Overview

**Indri** is a platform for creating, collaborating, and sharing algorithms, data visualizations, code snippets, and small apps. CodeLets can be viewed full screen or in web components that can be embedded in any web page.

Common uses include collaboration on algos, data visualization, embedding live code in documentation, and providing interactivity in programming sites.

## Areas

### Editor

The code *Editor* component is the large area at the top of a CodeLet. It contains the FM (File Manager) view on the left. When you click on a file in the FM, it will be loaded into the editor. The FM supports both cloud (default) and local file systems. 

### Console

The *Console* is an interactive REPL (**R**ead, **E**val, **P**rint, **L**oop). It allows you to type in code in the selected language and execute it immediately after hitting enter / return. For blocks such as the bodies of classes, statements and functions, it provides a secondary prompt. The exact behavior is language dependent.

After code in the Editor has been evaluated with the **Run** button (upper right corner), you can access its variables, functions, methods, and classes in the Console.

### Output

The *Output* is used similar to system out, but it supports rich media. You can print to it from the Editor using `print(...)` and from the Editor or Console using the "say" command, which is available in all supported languages.

**Example**

```
say("日本語", dict(
    fontSize="28pt",
    fontWeight="bold",
    color="rgb(180, 10, 10)",
    lineHeight="1.2"
))

say("🥷🦎🪼", dict(
    fontSize="120pt",
    lineHeight="1.2"
))

sayHTML("<img src='https://ikayzo.com/assets/stamp-about.png'/>")
```

## Sharing

CodeLets can be embedded as web components in any web page. Settings allow you to specify read, fork, and edit permissions for groups (lists of users), organizations, and public use. 

*Coming soon: Sharing live CodeLets in Slack.*

## Languages & Imports

CodeLets currently support [Python](https://www.python.org) and [TypeScript](https://www.typescriptlang.org). [Swift](https://www.swift.org) and [Kotlin](https://kotlinlang.org/) will be included in the next major release.

You can import libraries and access packages/namespaces supported by the language you are using. Here is an example of importing 'os' in Python using the Console:

```
> import os
> print(os.name)
posix
```

Here is another Python example of importing the greetES function from a file called spanish.py in the geetings folder. This time we use the Editor.

```
from greetings.spanish import greetES

greetES() # output "Hola 🎉"
```

*Note: If spanish.py is in the root you can simply write* `from spanish import greetES`.
