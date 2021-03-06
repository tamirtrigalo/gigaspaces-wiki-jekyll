---
layout: post
title:  Cheat Sheet
categories: HOWTO
weight:  700
parent:  none
---

{%summary%} Cheat sheet for GigaSpaces Documentation {%endsummary%}

# Text

{: .table .table-bordered}
| **Example** | **Markdown** |
| This is an *emphasised* text. | This is an \*emphasised\* text. |
| This is a **bold** text. | This is a \*\*bold\*\* text.  |
| This is a `monospaced` text | This is a \`monospaced\` text |

# Links

{: .table .table-bordered}
| **Description** | **Markdown** | **Output** |
| Link to external site | \[GigaSpaces\]\(http://www.gigaspaces.com\) | [GigaSpaces](http://www.gigaspaces.com) |
| Link to page in same folder | \[Directory Structure\]\(file-structure.html\) | [Directory Structure](file-structure.html) |
| Link to page in `xap` folder | \[SQL Query\]\({%raw%}{%currentjavaurl%}{%endraw%}/sqlquery.html\) | [SQL Query]({%currentjavaurl%}/sqlquery.html) |
| Link to page in `xapnet` folder | \[SQL Query\]\({%raw%}{%currentneturl%}{%endraw%}/sqlquery.html\) | [SQL Query]({%currentneturl%}/sqlquery.html) |
| Link to page in latest `xap` folder | \[SQL Query\]\({%raw%}{%latestjavaurl%}{%endraw%}/sqlquery.html\) | [SQL Query]({%latestjavaurl%}/sqlquery.html) |
| Link to page in latest `xapnet` folder | \[SQL Query\]\({%raw%}{%latestneturl%}{%endraw%}/sqlquery.html\) | [SQL Query]({%latestneturl%}/sqlquery.html) |
| Java doc of `org.openspaces.core.GigaSpace` | \[GigaSpace\]\({%raw%}{%javadoc org.openspaces.core.GigaSpace %}{%endraw%}\) | [GigaSpace]({%javadoc org.openspaces.core.GigaSpace %}) |
| .NET doc of `GigaSpaces.Core.ISpaceProxy` | \[ISpaceProxy\]\({%raw%}{%dotnetdoc GigaSpaces.Core.ISpaceProxy %}{%endraw%}\) | [ISpaceProxy]({%dotnetdoc GigaSpaces.Core.ISpaceProxy %}) |
| Link to latest Java Tutorial page | \[Getting started\]\({%raw%}{%latestjavatuturl%}/java-tutorial-part1.html){%endraw%}\) | [Getting Started]({%latestjavatuturl%}/java-tutorial-part1.html) |
| Link to latest .NET Tutorial page | \[Getting started\]\({%raw%}{%latestnettuturl%}/net-tutorial-part1.html){%endraw%}\) | [Getting Started]({%latestnettuturl%}/net-tutorial-part1.html) |


# Icons

{: .table .table-bordered}
| **Example** | **Markdown** |
| {%oksign%} This is an OK icon               | {%raw%} {%oksign%} This is an OK icon {%endraw%} |
| {%infosign%} This is an Info icon           | {%raw%} {%infosign%} This is an Info icon {%endraw%} |
| {%exclamation%} This is an Exclamation icon | {%raw%} {%exclamation%} This is an Exclamation icon {%endraw%} |
| {%question%} This is a Question icon        | {%raw%} {%question%} This is a Question icon {%endraw%} |
| {%plus%} This is a Plus icon                | {%raw%} {%plus%} This is a Plus icon {%endraw%} |
| {%remove%} This is a Remove icon            | {%raw%} {%remove%} This is a Remove icon {%endraw%} |
| {%star%} This is a Star icon                | {%raw%} {%star%} This is a Star icon {%endraw%} |
| {%lampon%} This is a Lamp On icon           | {%raw%} {%lampon%} This is a Lamp On icon {%endraw%} |
| {%lampoff%} This is a Lamp Off icon         | {%raw%} {%lampoff%} This is a Lamp Off icon {%endraw%} |
| {%download  This is a download   icon %}     | {%raw%} {%download  This is a download   icon %} {%endraw%} |
| {%pdf%} This is a pdf icon                  | {%raw%} {%pdf}% This is a pdf icon    {%endraw%} |
| {%zip  This is a zip icon%}               | {%raw%} {%zip  This is a zip icon  %}  {%endraw%} |
| {%folderopen%} This is an open folder icon  | {%raw%}{%folderopen%} This is an open folder icon  {%endraw%} |


{%next ur=./java-tutorial-part2.html|text=Next step in the tutorial is  %}

{%endnext%}


# Panels

<table border="1" cellpadding="10">
<colgroup><col span="1" style="width: 55%;"/><col span="1" style="width: 45%;"/></colgroup>
<tr><th> Example </th><th> Markdown </th></tr>
<tr><td>
{% highlight java linenos %}
public class Test {
    public void foo() {
        // TODO: ...
    }
}
{%endhighlight%}</td><td>{%raw%}<pre>
{% highlight java linenos %}
public class Test {
    public void foo() {
        // TODO: ...
    }
}
{%endhighlight%}
</pre>
Languages: java csharp xml
{%endraw%}</td></tr>
<tr><td>{%panel title=Foo| borderStyle=solid|borderColor=#3c78b5|bgColor=#FFFFCE%} This is a panel {%endpanel%}</td><td>{%raw%} {%panel title=Foo| borderStyle=solid|borderColor=#3c78b5|bgColor=#FFFFCE%} This is a panel {%endpanel%} {%endraw%}</td></tr>
<tr><td>{%tip title=Foo%}this is a Tip panel {%endtip%}</td><td>{%raw%} {%tip title=Foo%}this is a Tip panel {%endtip%} {%endraw%}</td></tr>
<tr><td>{%info title=Foo%}this is an Information panel {%endinfo%}</td><td>{%raw%} {%info title=Foo%}this is an Information panel {%endinfo%} {%endraw%}</td></tr>
<tr><td>{%note title=Foo%}this is a Note panel {%endnote%}</td><td>{%raw%} {%note title=Foo%}this is a Note panel {%endnote%} {%endraw%}</td></tr>
<tr><td>{%warning title=Foo%}this is a Warning panel {%endwarning%}</td><td>{%raw%} {%warning title=Foo%}this is a Warning panel {%endwarning%} {%endraw%}</td></tr>
<tr><td>{%quote%}This is a quote{%endquote%}</td><td>{%raw%} {%quote%}This is a quote{%endquote%} {%endraw%}</td></tr>
</table>

# Layout

### Table with borders

{: .table .table-bordered}
| Header1 | Header2 | Header3 |
|:--------|:--------|:--------|
| column1 | column2 | column3 |

Markdown:
<pre>
{: .table .table-bordered}
| Header1 | Header2 | Header3 |
|:--------|:--------|:--------|
| column1 | column2 | column3 |
</pre>

### Table without borders

{: .table }
| Header1 | Header2 | Header3 |
|:--------|:--------|:--------|
| column1 | column2 | column3 |

Markdown:
<pre>
| Header1 | Header2 | Header3 |
|:--------|:--------|:--------|
| column1 | column2 | column3 |
</pre>

### Tabbed Pane

<table border="1" cellpadding="10">
<colgroup><col span="1" style="width: 50%;"/><col span="1" style="width: 50%;"/></colgroup>
<tr><th> Example </th><th> Markdown </th></tr>
<tr><td>
{% inittab %}
{% tabcontent Foo %} This is tab Foo {% endtabcontent %}
{% tabcontent Bar %} This is tab Bar {% endtabcontent %}
{% endinittab %}
</td>
<td><pre>{%raw%}
{% inittab %}
{% tabcontent Foo %} This is tab Foo {% endtabcontent %}
{% tabcontent Bar %} This is tab Bar {% endtabcontent %}
{% endinittab %}
{%endraw%}</pre></td>
</tr>
</table>

### Section With Columns

<table border="1" cellpadding="10">
<colgroup><col span="1" style="width: 50%;"/><col span="1" style="width: 50%;"/></colgroup>
<tr><th> Example </th><th> Markdown </th></tr>
<tr><td>
{%section%}
{%column witdh=30%}This is column one{%endcolumn%}
{%column width=70%}This is column two{%endcolumn%}
{%endsection%}
</td><td><pre>{%raw%}
{%section%}
{%column witdh=30%}This is column one{%endcolumn%}
{%column width=70%}This is column two{%endcolumn%}
{%endsection%}
{%endraw%}</pre></td>
</tr>
</table>


### Cloak

<table border="1" cellpadding="10">
<colgroup><col span="1" style="width: 50%;"/><col span="1" style="width: 50%;"/></colgroup>
<tr><th> Example </th><th> Markdown </th></tr>
<tr><td>
{% togglecloak id=1 %}  **Click Here...**{% endtogglecloak %}
{% gcloak 1 %}
- Foo
- Bar
{% endgcloak %}
</td><td><pre>{%raw%}
{% togglecloak id=1 %}  **Click Here...**{% endtogglecloak %}
{% gcloak 1 %}
- Foo
- Bar
{% endgcloak %}
{%endraw%}</pre></td>
</tr>
</table>

# Macros

{: .table .table-bordered}
| **Description** | **Macro** | **Output** |
| Latest XAP Release  | {%raw%} {%latestxaprelease%} {%endraw%} | {%latestxaprelease%} |
| Latest Cloudify Release version | {%raw%} {%latestcloudifyrelease%} {%endraw%} | {%latestcloudifyrelease%} |
| Latest XAP Release file name | {%raw%} {%version build-filename %} {%endraw%} | {%version build-filename %} |
| Latest XAP Release home dir | {%raw%} {%version gshome-directory %} {%endraw%} | {%version gshome-directory %} |
| Latest Default Lookup Group | {%raw%} {%version default-lookup-group %} {%endraw%} | {%version default-lookup-group %} |
| Latest XAP Maven | {%raw%} {%version maven-version %} {%endraw%} |{%version maven-version %} |


# Jar versions

{: .table .table-bordered}
| **Description** | **Macro** | **Output** |
| spring  | {%raw%} {%version spring %} {%endraw%} |{%version spring %} |
| antlr4-runtime  | {%raw%} {%version antlr4-runtime %} {%endraw%} |{%version antlr4-runtime %} |
| mongo-java-driver  | {%raw%} {%version mongo-java-driver %} {%endraw%} |{%version mongo-java-driver %} |
| mongo-datasource  | {%raw%} {%version mongo-datasource %} {%endraw%} |{%version mongo-datasource %} |
| openjpa  | {%raw%} {%version openjpa %} {%endraw%} |{%version openjpa %} |





# Custom

### Align

<table border="1" cellpadding="10">
<colgroup><col span="1" style="width: 50%;"/><col span="1" style="width: 50%;"/></colgroup>
<tr><th> Example </th><th> Markdown </th></tr>
<tr><td>{%align left%} Aligned to left {%endalign%}</td><td>{%raw%} {%align left%} Aligned to left {%endalign%} {%endraw%}</td></tr>
<tr><td>{%align center%} Aligned to center {%endalign%}</td><td>{%raw%} {%align center%} Aligned to center {%endalign%} {%endraw%}</td></tr>
<tr><td>{%align right%} Aligned to right {%endalign%}</td><td>{%raw%} {%align right%} Aligned to right {%endalign%} {%endraw%}</td></tr>
</table>

### Custom Colors

{: .table .table-bordered}
| **Example** | **Markdown** |
| This text has {%color blue%}blue{%endcolor%} color | {%raw%} This text has {%color blue%}blue{%endcolor%} color {%endraw%} |
| This text has {%bgcolor orange %}orange background{% endbgcolor %} | {%raw%} This text has {%bgcolor orange %}orange background{% endbgcolor %} {%endraw%} |
| This is a line with a {%wbr%} word break | {%raw%} This is a line with a {%wbr%} word break {%endraw%} |

### Custom Text Size

<table border="1" cellpadding="10">
<colgroup><col span="1" style="width: 50%;"/><col span="1" style="width: 50%;"/></colgroup>
<tr><th> Example </th><th> Markdown </th></tr>
<tr><td>{%fontsize 10%}This is font 10{%endfontsize%}</td><td>{%raw%} {%fontsize 10%}This is font 10{%endfontsize%} {%endraw%}</td></tr>
<tr><td>{%fontsize 20%}This is font 20{%endfontsize%}</td><td>{%raw%} {%fontsize 20%}This is font 20{%endfontsize%} {%endraw%}</td></tr>
<tr><td>{%fontsize 30%}This is font 30{%endfontsize%}</td><td>{%raw%} {%fontsize 30%}This is font 30{%endfontsize%} {%endraw%}</td></tr>
</table>


# Image Popup

<table border="1" cellpadding="10">
<colgroup><col span="1" style="width: 50%;"/><col span="1" style="width: 50%;"/></colgroup>
<tr><th> Example </th><th> Markdown </th></tr>
<tr><td>{% popup /attachment_files/qsg/class_diagram.png| Class Diagram| Class Diagram %}</td><td>{%raw%} {% popup /attachment_files/qsg/class_diagram.png| Class Diagram| Class Diagram %} {%endraw%}</td></tr>
</table>


# Youtube Video

<table border="1" cellpadding="10">
<colgroup><col span="1" style="width: 50%;"/><col span="1" style="width: 50%;"/></colgroup>
<tr><th> Example </th><th> Markdown </th></tr>
<tr><td>{%youtube V7rbbmWo3JU | Multi Site Deployment%}</td><td>{%raw%} {%youtube V7rbbmWo3JU | Multi Site Deployment%} {%endraw%}</td></tr>
</table>

# Accordion 1

<table border="1" cellpadding="10">
<colgroup><col span="1" style="width: 50%;"/><col span="1" style="width: 50%;"/></colgroup>
<tr><th> Example </th><th> Markdown </th></tr>
<tr><td>{%accordion id=acc1%}{%accord title=Java | parent=acc1%}Java Code fdsfdsfdsfdsfdsfdfdfdfdsfdfdfdsfdsfdfdfdsf{%endaccord%}{%accord title=c# | parent=acc1%}c# Code{%endaccord%}{%endaccordion%}</td><td>{%raw%} {%accordion id=acc1%}{%accord title=Java | parent=acc1%}Java Code{%endaccord%}{%accord title=c# | parent=acc1%}c# Code{%endaccord%}{%endaccordion%} {%endraw%}</td></tr>
</table>


# Accordion 2

{%accordion id=acc10%}

{%accord title=Java | parent=acc10%}
{%inittab%}
{%tabcontent Author Entity%}
{%highlight java%}
class AuthorEntity
{

}
{%endhighlight%}
{%endtabcontent%}
{%tabcontent Book Entity%}
{%highlight java%}
class BookEntity
{

}
{%endhighlight%}
{%endtabcontent%}
{%endinittab%}
{%endaccord%}

{%accord title=C# | parent=acc10%}
{%inittab%}
{%tabcontent Author Entity%}
{%highlight c#%}
class AuthorEntity
{

}
{%endhighlight%}
{%endtabcontent%}
{%tabcontent Book Entity%}
{%highlight csharp%}
class BookEntity
{

}
{%endhighlight%}
{%endtabcontent%}
{%endinittab%}
{%endaccord%}

{%endaccordion%}



# Learn More

{%panel  bgColor=#FFFFCE%}
{%section width=10% %}
{%column%}

{%endcolumn%}
{%column width=90% %}
Learn more about this issue by visiting this page  !
{%endcolumn%}
{%endsection%}
{%endpanel%}


# Refer

{%refer %}
This should be used to refer to related subjects !
{%endrefer%}