# Coldfusion Style Guide

## Table of Contents

* [Source Code Layout](#source-code-layout)
* [Syntax](#syntax)
* [Strings](#strings)
* [SQL](#sql)

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

* <a name="camelCase-resourceBundle"></a>
  Prefer **camelCase** for resource bundle variables.
<sup>[[link](#camelCase-resourceBundle)]</sup>
```Coldfusion
# bad - resource bundle with SnakeCase
<cfoutput>
	#request.rb('FooBar')#
</cfoutput>

# good
<cfoutput>
	#request.rb('fooBar')#
</cfoutput>
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

* <a name="conditional-comparison"></a>
  Prefer using a positive comparison in an if statement rather than a double negative.
<sup>[[link](#conditional-comparison)]</sup>

```Coldfusion
# bad - double negative comparison
<cfif fooBarQuery.queryCount neq 0>
</cfif>

# good
<cfif fooBarQuery.queryCount gt 0>
</cfif>
```

* <a name="comparison"></a>
  Prefer using lowercase english words when comparing multiple variables in a conditional.
<sup>[[link](#comparison)]</sup>
```Coldfusion
# bad - use of && and ||
<cfif (variables.isFooBar && variables.isBarFoo) || variables.isAllTheFooBars>
</cfif>

# good
<cfif (variables.isFooBar and variables.isBarFoo) or variables.isAllTheFooBars>
</cfif>
```

## Strings

* <a name="string-interpolation"></a>
  Prefer string interpolation rather than string concatenation
<sup>[[link](#string-interpolation)]</sup>

```Coldfusion
# bad - string concatenation
<cfset variables.fooBar='The brown fox' & variables.label & 'the fence.'>

# good
<cfset variables.fooBar="The brown fox #variables.label# the fence.">
```

## SQL

* <a name="with-no-lock"></a>
  Use `WITH(NOLOCK)` on all select statements to prevent locking the database table for others. (MSSQL specific)
<sup>[[link](#with-no-lock)]</sup>

```Coldfusion
# bad - no WITH(NOLOCK)
<cfquery name="fooBar" datasource="#datasource#">
SELECT *
FROM fooBarTable
</cfquery>

# good
<cfquery name="fooBar" datasource="#datasource#">
SELECT *
FROM fooBarTable WITH(NOLOCK)
</cfquery>
```

* <a name="uppercase-sql"></a>
  Uppercase all SQL functions and reserved words. (MSSQL specific)
<sup>[[link](#uppercase-sql)]</sup>

```Coldfusion
# bad - all SQL functions/words are lowercase
<cfquery name="fooBar" datasource="#datasource#">
select top 1 *, count(*)
from fooBarTable with(nolock)
where columnName like '%foo%'
	and columnName2 = 'bar'
</cfquery>

# good
<cfquery name="fooBar" datasource="#datasource#">
SELECT TOP 1 *, COUNT(*)
FROM fooBarTable WITH(NOLOCK)
WHERE columnName LIKE '%foo%'
	AND columnName2 = 'bar'
</cfquery>
```
