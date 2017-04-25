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