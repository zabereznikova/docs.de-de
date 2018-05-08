### <a name="icommandcanexecutechanged-event-behaviour-changed-in-net-45"></a>Das ICommand.CanExecuteChanged-Ereignisverhalten wurde in .NET 4.5 geändert.

|   |   |
|---|---|
|Details|In .NET Framework 4.5 wurde ein <xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=name> ignoriert, sofern der Absender des Ereignisses nicht dasselbe Objekt wie das Objekt gewesen ist, das das Ereignis ausgelöst hat. Dieses Problem wurde in Wartungsupdates von .NET Framework 4.5 behoben.|
|Vorschlag|Dieses Problem wurde in Wartungsreleases von .NET Framework 4.5 behoben, daher kann es vermieden werden, indem Sie sicherstellen, dass .NET Framework auf dem neuesten Stand ist. Sie können auch ein Upgrade auf .NET Framework 4.5.1 durchführen. Alternativ kann <xref:System.Windows.Input.ICommand?displayProperty=name> verwendender Code geändert werden, um sicherzustellen, dass der Absender beim Auslösen eines <xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=name>-Befehls dasselbe Objekt ist, das auch das Ereignis auslöst hat.|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=nameWithType></li></ul>|
|Analyzer|<ul><li>CD0084</li></ul>|

