---
layout: post102
title:  Scala
categories: XAP102
parent: interoperability-overview.html
weight: 400
---

<br>

{%section%}
{%column width=10% %}
![data-access.jpg](/attachment_files/subject/scala.jpeg)
{%endcolumn%}
{%column width=90% %}
Several extensions to the XAP API have been introduced to provide a more natural way of combining Scala with XAP.
{%endcolumn%}
{%endsection%}

<br>

{%fpanel%}
[Constructor based properties](./scala-constructor-based-properties.html){%wbr%}
The com.gigaspaces.annotation.pojo.SpaceClassConstructor annotation on a constructor will cause the data class properties analysis to be based on properties found in the constructor (instead of getters/setters).

[Enhanced REPL](./scala-enhanced-repl.html){%wbr%}
Following is a short demo of what can be done with the XAP scala shell. It should be noted that this shell is a regular Scala REPL with some initial imports and initialization code.

[Predicate based queries](./scala-predicate-based-queries.html){%wbr%}
Support for predicate based queries on the GigaSpace proxy has been added in. This support is based on the new macros feature introduced in Scala.

[Scripting Executor](./scala-scripting-executor.html){%wbr%}
Dynamic Language Tasks have been extended and now support Scala based script execution.

[Task Execution](./scala-task-execution.html){%wbr%}
A wrapper around the XAP API provides some sugaring on top of the GigaSpace#execute methods.

[Exemplary Project](./scala-exemplary-project.html){%wbr%}
There has been created a project that shows how certain features of XAP Scala can be used in real project and how Scala and Java code might be integrated.
{%endfpanel%}
<br>

{% info %}
The Scala version required in order to use the Scala Openspaces extension is 2.11.x - up to 2.11.6.
{% endinfo %}

Assuming there is a scala installation under `$SCALA_HOME`, the jars under `$SCALA_HOME/lib` should be copied to `$GS_HOME/lib/platform/scala/lib`.
Another options is to change `setenv.{bat,sh`} so that `$SCALA_JARS` points to `$SCALA_HOME/lib`.
