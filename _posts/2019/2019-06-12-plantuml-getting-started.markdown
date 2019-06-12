---
layout: "post"
title: "PlantUML: Getting Started"
date: "2019-06-12 18:31"
---

## Introduction

In my [previous post][0cd23a76], I talked about how PlantUML is much better than most diagram tools out there for developers. Check it out if you're curious about PlantUML.

## First Steps

The best ways to start are:
* [Online servlet](http://www.plantuml.com/plantuml)
*  [PlantUML Previewer](http://sujoyu.github.io/plantuml-previewer/) ( Vim/Emacs enabled if you choose "Ace" and select the binding from the dropdown that appears).

You can check out the "Installation" section below for alternatives, plugins and integrations -- but for now, these pages will do just fine.

## Component diagrams

The following code will generate a simple Component Diagram:

```
package [Database]
[Database] <-down-> [Backend]
[Backend] <-d-> [Frontend]
```
![Component Diagram](/images/2019/06/component-diagram.png)

Let's take a look at what is happening here.
1. `[Database]` is being created using a `package` declaration.
2. `[Database]` is connected to a `[Backend]` which is created inline.
3. `[Backend]` is connected to a `Frontend` which is created inline.
4. `<-down->` and `<-d->` are the exact same thing. These are connections between components. The `down` or `d` specifies that the 2nd component is below the 1st component.

And voila, you have a neat little diagram in 3 lines of code.

## Component diagrams with styles and labels

Let's add some color and labels into this world

```
skinparam component {
  FontColor white
}

package [Database] #red
package [Backend] #green
package [Frontend] #blue

[Database] <-down-> [Backend] #orange : DB Connection
[Backend] <-d-> [Frontend] #orange : REST API
```

![Colored Components](/images/2019/06/colored-components.png)

As you can see:
1. `skinparam component` is the style "class" for the `component` object. Inside it, we are setting `FontColor` to white.
2. The packages are all being colored individually. Note that all the fonts are now white thanks to `skinparam`.
3. The arrows are also being colored orange (using `#`)
4. The arrows now have labels (using `:`)

## Sequence diagrams

PlantUML also lets you build sequence diagrams, which can come in real handy. Check this out:
```
Frontend --> Backend : POST /login
Backend --> Frontend : Login success, return token
Frontend --> Backend : POST /create
Backend --> Database : Insert new object
Database --> Backend : Return new object
Backend --> Frontend : Return new object
```
![Sequence Diagram](/images/2019/06/sequence-diagram.png)

This is pretty self-explanatory, and is easy to understand if you followed the previous examples.

## Styled sequence diagrams

These can be styled as well. The following example is from the PlantUML website. As you can see, PlantUML is pretty powerful!

```
@startuml
skinparam backgroundColor #EEEBDC
skinparam handwritten true

skinparam sequence {
	ArrowColor DeepSkyBlue
	ActorBorderColor DeepSkyBlue
	LifeLineBorderColor blue
	LifeLineBackgroundColor #A9DCDF

	ParticipantBorderColor DeepSkyBlue
	ParticipantBackgroundColor DodgerBlue
	ParticipantFontName Impact
	ParticipantFontSize 17
	ParticipantFontColor #A9DCDF

	ActorBackgroundColor aqua
	ActorFontColor DeepSkyBlue
	ActorFontSize 17
	ActorFontName Aapex
}

actor User
participant "First Class" as A
participant "Second Class" as B
participant "Last Class" as C

User -> A: DoWork
activate A

A -> B: Create Request
activate B

B -> C: DoWork
activate C
C --> B: WorkDone
destroy C

B --> A: Request Created
deactivate B

A --> User: Done
deactivate A

@enduml
```

![Colored Sequence Diagram](/images/2019/06/colored-sequence-diagram.png)

There's a lot happening here, but again, all of this is fairly easy to understand if you understand the previous examples and read the documentation.

## Installation and Useful Links

If you'd like to install PlantUML or integrate it with a tool you use, check out the following list.

* [Command Line](http://plantuml.com/command-line)
* [Microsoft Word](http://plantuml.com/word)
* [Open Office](http://sourceforge.net/projects/plantuml/files/plantuml.odt/download)
* [Slack](https://github.com/taichi/umlbot)
* [Visual Studio Code - 1](https://marketplace.visualstudio.com/items?itemName=okazuki.okazukiplantuml)
* [Visual Studio Code - 2](https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml)
* [Sublime Text](https://github.com/jvantuyl/sublime_diagram_plugin)
* [Emacs](http://plantuml.com/emacs)
* [Vim](http://www.vim.org/scripts/script.php?script_id=3538)
* [IntelliJ](http://plugins.intellij.net/plugin/?idea&id=7017)
* [Eclipse](http://plantuml.com/eclipse)

You can see more ways to run PlantUML [here](http://plantuml.com/running).

You can see documentation [here](http://plantuml.com/guide).



  [0cd23a76]: /2019/06/11/the-shockingly-fun-diagram-tool-that-will-change-your-life-as-a-programmer-plantuml.html "The shockingly fun diagram tool that will change your life as a programmer: PlantUML"
