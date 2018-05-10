### <a name="listlttgtforeach-can-throw-exception-when-modifying-list-item"></a>List&lt;T&gt;.ForEach kann beim Ändern eines Listenelements eine Ausnahme auslösen

|   |   |
|---|---|
|Details|Ab .NET Framework 4.5 löst ein <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})>-Enumerator eine <xref:System.InvalidOperationException?displayProperty=name>-Ausnahme aus, wenn ein Element in der aufrufenden Sammlung geändert wird. Zuvor hätte dies keine Ausnahme ausgelöst, aber zu Racebedingungen geführt.|
|Vorschlag|Im Idealfall sollte der Code unveränderlich sein, damit Listen nicht geändert werden, während ihre Elemente aufgezählt werden, da dies nie ein sicherer Vorgang ist. Eine App kann auf .NET Framework 4.0 ausgelegt werden, um zum vorherigen Verhalten zurückzukehren.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType></li></ul>|

