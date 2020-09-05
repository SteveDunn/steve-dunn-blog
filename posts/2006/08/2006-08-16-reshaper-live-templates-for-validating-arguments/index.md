---
title: "Reshaper Live Templates for validating arguments"
date: "2006-08-16"
---

I strongly agree with the ['contract](http://www.regdeveloper.co.uk/2005/12/29/first_among_equals/)' mataphor in API design, hence my interest in [Spec#](http://research.microsoft.com/specsharp/) (that I've [blogged about before](http://stevedunns.blogspot.com/2006/08/spec.html)).  

To assist in this and to eliminate the tedium of writing argument checks, I've created 3 Resharper Live Templates.  These check for

- null parameters for any object passed
- invalid parameters for any object passed
- null or empty check for any String passed. 

These templates are called **'arg'**, **'argnull'** and **'argempty'** respectivly.

Resharper 1.5 doesn't allow importing or exporting of Live Templates from the GUI.  They are however stored in an XML file at %userprofile%Application DataJetBrainsReSharperUserSettings.xml.   Below is a chunk of XML that must be placed under the TemplateManagerTemplates node.  If you have any others, please let me know!

> <Template text="if( $TYPE$$EXPRESSION$ )&#xA; throw new ArgumentException( @&quot;Cannot $ACTION$ as the value passed was invalid. Please provide a valid value.&quot;, @&quot;$TYPE$&quot; ) ;&#xA;" shortcut="arg" description="Throws an ArgumentException" kind="livetemplate" reformat="false" fileMask="" context="Everywhere" fileContext="CSharp" enabled="False" id="1723695683">
> 
> <Variables>
> 
> <Variable name="TYPE" expression="variableOfType(&quot;System.Object&quot;)" initialRange="0" />
> 
> <Variable name="EXPRESSION" expression="constant(&quot; != 1&quot;)" initialRange="0" />
> 
> <Variable name="ACTION" expression="constant(&quot;PERFORM AN ACTION&quot;)" initialRange="0" />
> 
> </Variables>
> 
> </Template>
> 
> <Template text="if( $TYPE$ == null || $TYPE$.Length == 0 )&#xA;throw new ArgumentNullException( @&quot;$TYPE$&quot;, @&quot;Cannot $ACTION$ as the value passed was null or empty. Please provide a valid non null value.&quot; ) ;&#xA;" shortcut="argempty" description="Throws an ArgumentNullException when a string is null or empty" kind="livetemplate" reformat="true" fileMask="" context="Everywhere" fileContext="CSharp" enabled="False" id="1705884294">
> 
> <Variables>
> 
> <Variable name="TYPE" expression="variableOfType(&quot;System.String&quot;)" initialRange="0" />
> 
> <Variable name="ACTION" expression="constant(&quot;PERFORM AN ACTION&quot;)" initialRange="0" />
> 
> </Variables>
> 
> </Template>
> 
> <Template text="if( $TYPE$ == null )&#xA;throw new ArgumentNullException( @&quot;$TYPE$&quot;, @&quot;Cannot $ACTION$ as the value passed was null. Please provide a valid non-null value.&quot; ) ;&#xA;" shortcut="argnull" description="Throws an ArgumentNullException" kind="livetemplate" reformat="true" fileMask="" context="Everywhere" fileContext="CSharp" enabled="False" id="1497171628">
> 
> <Variables>
> 
> <Variable name="TYPE" expression="variableOfType(&quot;System.Object&quot;)" initialRange="0" />
> 
> <Variable name="ACTION" expression="constant(&quot;PERFORM AN ACTION&quot;)" initialRange="0" />
> 
> </Variables>
> 
> </Template>
