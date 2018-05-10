### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a>WPF TextBox verwendet standardmäßig 100 als Grenzwert für die Aktion „Rückgängig machen“

|   |   |
|---|---|
|Details|In .NET Framework 4.5 beträgt der Standardgrenzwert für ein WPF-Textfeld 100 (im Gegensatz zu .NET Framework 4.0, bei dem der Wert unbegrenzt ist).|
|Vorschlag|Wenn der Grenzwert von 100 für die Aktion „Rückgängig machen“ zu niedrig ist, kann er explizit mit <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit> festgelegt werden.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|

