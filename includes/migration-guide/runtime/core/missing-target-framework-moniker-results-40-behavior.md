### <a name="missing-target-framework-moniker-results-in-40-behavior"></a>Fehlender Zielframeworkmoniker führt zum Verhalten der Version 4.0

|   |   |
|---|---|
|Details|Anwendungen, bei denen auf Assemblyebene kein <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> angewendet wurde, werden automatisch mit der Semantik (den Quirks) von .NET Framework 4.0 ausgeführt. Um eine hohe Qualität sicherzustellen, empfiehlt es sich, dass alle Binärdateien ein <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> als Attribut erhalten, wodurch die Version von .NET Framework angegeben wird, mit denen sie erstellt wurden. Beachten Sie, dass die Verwendung eines Zielframeworkmonikers in einer Projektdatei dazu führt, dass MSBuild automatisch ein <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> anwendet.|
|Vorschlag|Es sollte ein <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> bereitgestellt werden, entweder durch direktes Hinzufügen des Attributs zur Assembly oder durch Angeben eines Zielframeworks in der [Projektdatei oder über die Visual Studio-GUI für Projekteigenschaften](http://blogs.msdn.com/b/visualstudio/archive/2010/05/19/visual-studio- managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework.aspx).|
|Bereich|Hauptversion|
|Version|4.5|
|Typ|Laufzeit|

