### <a name="unexpected-invalidcastexception-from-invokemethod-activity-in-wf4"></a>Unerwartete InvalidCastException aus der InvokeMethod-Aktivität in WF4

|   |   |
|---|---|
|Details|Die Verwendung von <xref:System.Activities.Statements.InvokeMethod>, die auf eine Methode mit einem Parameter, der NULL-Werte zulässt, abzielt, kann <xref:System.InvalidCastException?displayProperty=name> auslösen.|
|Vorschlag|Dieses Verhalten wurde in einem Wartungsupdate für .NET Framework 4.5 rückgängig gemacht. Aktualisieren Sie .NET Framework 4.5, oder führen Sie ein Upgrade auf .NET Framework 4.5.1 oder höher aus, um dieses Problem zu beheben.|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Activities.Statements.InvokeMethod.Parameters?displayProperty=nameWithType></li></ul>|
|Analyzer|<ul><li>CD0088</li></ul>|

