# Coldfusion Style Guide

## Table of Contents

* [Source Code Layout](#source-code-layout)
* [Syntax](#syntax)

## Source Code Layout

> Nearly everybody is convinced that every style but their own is
> ugly and unreadable. Leave out the "but their own" and they're
> probably right... <br>
> -- Jerry Coffin (on indentation)

* <a name="utf-8"></a>
  Use `UTF-8` as the source file encoding.
<sup>[[link](#tabs-indentation)]</sup>

* <a name="tabs-indentation"></a>
  Use one **tab** per indentation level.
<sup>[[link](#tabs-indentation)]</sup>

```Coldfusion
# bad - two tabs
<cffunction name="fooBar">
		<cfargument name="foo">
</cffunction>

# good
<cffunction name="fooBar">
	<cfargument name="foo">
</cffunction>
```
## Syntax

* <a name="self-closing-tag"></a>
  Use one space between the end of the line and the self closing tag
<sup>[[link](#self-closing-tag)]</sup>

```Coldfusion
# bad - no space
<set name="fooBar" value="#fooBarValue#"/>

# good
<set name="fooBar" value="#fooBarValue#" />
```

* Never use self closing tags unless you are coding XML (where they are required)

```Coldfusion
# bad - do not use self closing tags in cfm or cfc files
<cfset variables.fooBar='I am located in a cfm file' />

# good
<cfset variables.fooBar='I am located in a cfm file'>
```

* <a name="camelCase"></a>
  Use **camelCase** for variables, functions, and argument names.
<sup>[[link](#camelCase)]</sup>
```Coldfusion
# bad - Function/argument with SnakeCase
<cffunction name="Init">
	<cfargument name="MyObjectId">
</cffunction>

# good
<cffunction name="init">
	<cfargument name="myObjectID">
	...
</cffunction>

# bad - `Id` should be uppercase
<cfset variables.websiteId=12345>

# good
<cfset variables.websiteID=12345>

# bad - Acronyms at the beginning of a variable should be all lowercase
<cfset variables.POSProfileID=12345>

# good
<cfset variables.posProfileID=12345>
```

* <a name="SnakeCase"></a>
  Use **SnakeCase** for object names.
<sup>[[link](#SnakeCase)]</sup>
```Coldfusion
# bad - Object with camelCase
<cfcomponent displayname="myObject">

# good
<cfcomponent displayname="MyObject">
```
