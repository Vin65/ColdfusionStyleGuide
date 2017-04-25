# Coldfusion Style Guide

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

* <a name="self-closing-tag"></a>
  Use one space between the end of the line and the self closing tag
<sup>[[link](#self-closing-tag)]</sup>

```Coldfusion
# bad - no space
<cfparam name="attributes.fooBarIDs" default=""/>

# good
<cfparam name="attributes.fooBarIDs" default="" />
```

* <a name="camelCase"></a>
  Use **camelCase** for variables, functions, and argument names.
<sup>[[link](#camelCase)]</sup>
```Coldfusion
# bad - Function/argument with SnakeCase
<cffunction name="Init" access="package" output="false" returntype="CartObject">
	<cfargument name="MyObjectId" type="string" required="true">
</cffunction>

# good
<cffunction name="init" access="package" output="false" returntype="CartObject">
	<cfargument name="myObjectID" type="string" required="true">
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
<cfcomponent displayname="myObject" extends="vin65.basecomponent">

# good
<cfcomponent displayname="MyObject" extends="vin65.basecomponent">
```
