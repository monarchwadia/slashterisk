---
layout: "post"
title: "Java bugfix for generated sources not being picked up"
date: "2019-06-19 21:10"
---

I was using `swagger-codegen-maven-plugin` to generate entities using Apache CXF. The project was successfully generating entities in the `target` folder. IntelliJ was also correctly picking the generated entities up.

However, build was failing with `package io.swagger.model does not exist` errors.

I followed [this StackOverflow answer][f6cd6ef9] to resolve the issue. I used the `build-helper-maven-plugin` with the following config:

```xml
<plugin>
    <groupId>org.codehaus.mojo</groupId>
    <artifactId>build-helper-maven-plugin</artifactId>
    <executions>
        <execution>
            <phase>generate-sources</phase>
            <goals>
                <goal>add-source</goal>
            </goals>
            <configuration>
                <sources>
                    <source>${project.build.directory}/generated-sources/swagger</source>
                </sources>
            </configuration>
        </execution>
    </executions>
</plugin>
```

### Observations & notes

I've been thinking about Java lately. I'm more and more of the opinion that a lot of the interesting architecture work in Java revolves around dealing with issues in the language (and tooling, and ecosystem, and community) itself, rather than real business logic. This issue just underscores my feelings -- I wish Maven just picked up these sources automatically.

  [f6cd6ef9]: https://stackoverflow.com/questions/19633505/why-are-maven-generated-sources-not-getting-compiled "Why are Maven generated-sources not getting compiled? [duplicate]"
