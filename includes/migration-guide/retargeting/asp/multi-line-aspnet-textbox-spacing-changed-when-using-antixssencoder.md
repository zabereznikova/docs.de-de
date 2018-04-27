### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>Der Abstand für mehrzeilige ASP.NET-Textfelder (TextBox) wurde bei der Verwendung von AntiXSSEncoder geändert

|   |   |
|---|---|
|Details|In .NET Framework 4.0 wurden zwischen Zeilen eines mehrzeiligen Textfelds beim Postback zusätzliche Zeilen eingefügt, wenn <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=name> verwendet wird. In .NET Framework 4.5 sind diese zusätzlichen Zeilenumbrüche nicht enthalten, wenn die Web-App auf .NET 4.5 ausgerichtet ist.|
|Vorschlag|Beachten Sie, dass bei Web-Apps der Version 4.0, die auf .NET 4.5 neu ausgerichtet wurden, mehrzeilige Textfelder möglicherweise verbessert wurden, damit diese keine zusätzlichen Zeilenumbrüche mehr einfügen. Wenn dies nicht erwünscht ist, kann die App das alte Verhalten verwenden, wenn sie unter .NET Framework 4.5 ausgeführt wird, indem sie auf .NET Framework 4.0 ausgerichtet wird.|
|Bereich|Gering|
|Version|4.5|
|Typ|Neuzuweisung|

