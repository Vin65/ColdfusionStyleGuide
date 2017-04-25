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
  Use **camelCase** for variables, functions, and argument names. Use **SnakeCase** for object names.
<sup>[[link](#camelCase)]</sup>
```Coldfusion
# bad - Object with camelCase and function/argument with SnakeCase
<cfcomponent displayname="myObject" extends="vin65.basecomponent">
	<cffunction name="Init" access="package" output="false" returntype="CartObject">
		<cfargument name="MyObjectId" type="string" required="true">
		...
	</cffunction>
</cfcomponent>

# good
<cfcomponent displayname="MyObject" extends="vin65.basecomponent">
	<cffunction name="init" access="package" output="false" returntype="CartObject">
		<cfargument name="myObjectID" type="string" required="true">
		...
	</cffunction>
</cfcomponent>
```
