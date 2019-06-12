---
layout: "post"
title: "The shockingly fun diagram tool that will change your life as a programmer: PlantUML"
date: "2019-06-11 23:10"
---

## Why programmers hate diagrams

Programmers don't hate diagrams, they hate *diagram tools*. That's because most diagram tools were built for muggles and really suck for programmers.

Here's what I mean:

Me, a developer  |  Diagram tools
--|--
Prefer using my keyboard. I hate using my mouse.  |  Most are mouse-driven.
I like using classes to organize style definitions (fonts & colors). |  Most have no concept of reusable styles.
I like seeing changes happen automatically.  |  Most diagram tools offer little automation and demand tedious, manual work and rework.
I like quickly refactoring my work with a few keystrokes (preferably using a statically typed language in an IDE). | Most have no concept of refactoring -- redrawing lines really, really sucks.
I like learning the intricacies of the tools I'm working with.  |  Most diagram tools are shallow GUIs.

## How PlantUML shines

PlantUML is a lightweight markup language that generates diagrams. Mindblowing, I absolutely love it. Three things set PlantUML apart:
* You code your diagram definition instead of painting it on the screen.
* The syntax for drawing arrows is `component1 <--> component1`.
* PlantUML automatically arranges and balances your components and arrows.
* You can iterate really quickly. I have wowed clients while iterating through diagrams on a projector.

## Examples of PlantUML diagrams

The following examples are all taken from [Real World PlantUML][9fd06373]
### Class Diagram


![Simple class diagram](/images/2019/06/simple-class-diagram.png)

```PlantUML
@startuml

Class Student

Class FlashCards
Class Questions
Class Answers


Student"1" -- "+"FlashCards : Interacts with >

FlashCards"1" o-- "1"Questions : has >
FlashCards"1" o-- "1"Answers : has >
Answers"1" *-- "1"Wrong : has >
Answers"1" *-- "1"Right : has >



@enduml
```

### Sequence Diagram, non-english characters and background colors
![Sequence diagram with chinese characters](/images/2019/06/sequence-diagram-with-chinese-characters.png)

```PlantUML
@startuml

    skinparam backgroundColor #EEEBDC
    actor 使用者
    participant " 頭等艙" as A
    participant " 第二類" as B
    participant " 最後一堂課" as 別的東西
    使用者-> A: 完成這項工作
    activate A
    A -> B: 創建請求
    activate B
    B -> 別的東西: 創建請求
    activate 別的東西
    別的東西--> B: 這項工作完成
    destroy 別的東西
    B --> A: 請求創建
    deactivate B
    A --> 使用者: 做完
    deactivate A

    @enduml
```
![Sequence diagram with boxes](/images/2019/06/sequence-diagram-with-boxes.png)

```plantuml
@startuml
	participant terminal

	box "Crédit Chaton" #99CCFF
		participant acquisition as acqChaton
		participant autorisation as authChaton
	end box

	participant interbancaire

	box "Bénépé" #FFCC99
		participant acquisition as acqBé
		participant autorisation as authBé
	end box

	terminal -> acqChaton : demande
	acqChaton -> interbancaire :demande
	interbancaire -> acqBé : demande
	acqBé -> authBé : demande
	authBé --> acqBé : réponse
	acqBé --> interbancaire : réponse
	interbancaire --> acqChaton : réponse
	acqChaton --> terminal : réponse
@enduml
```

### Activity Diagrams

![Activity Diagram](/images/2019/06/activity-diagram.png)

```plantuml
@startuml

title Delete review

(*) --> "User clicks on delete review"
    --> if "Review is owned by user"
    	--> [Success] "Delete review from DB"
	--> "Display success message"
	--> (*)    
    else
	--> [Failure] "Display error message"
	--> (*)
    endif

@enduml
```

## PlantUML's limitations

Like all good purpose-built tools, there are also some limitations:
* PlantUML's diagrams are clean and tidy, but not as beautiful as other tools.
* PlantUML is great for basic diagrams, but complex compositions are out of its purview.
* PlantUML does not support multipage diagrams.
* PlantUML does not support links between diagrams.

## Please upgrade your life and use PlantUML

PlantUML helped me discover that the only thing wrong with diagrams is how bad most diagram tools are.

PlantUML is useful for students, junior developers, senior developers, team leads, dev managers, solutions architects, enterprise architects, technical project managers and CTOs. In short, if you can code, you should absolutely do yourself a favour and spend a few hours learning PlantUML.

## Why you should trust me

Source: I've been using PlantUML for 5 years and I absolutely love it. PlantUML saved my developer-soul as a consultant working with corporations. My clients often(and for good reason) need ideas rendered in a shareable, visual format that can be put up on slides and passed around in PDFs.

[9fd06373]: https://real-world-plantuml.com "Real World PlantUML"
