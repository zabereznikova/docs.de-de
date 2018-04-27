### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>In einem WPF-TextBox-Element markierter Text wird in einer anderen Farbe angezeigt, wenn das Textfeld inaktiv ist

|   |   |
|---|---|
|Details|Wenn in .NET 4.5 ein WPF-Textfeldsteuerelement inaktiv ist (nicht den Fokus besitzt), wird der im Feld markierte Text in einer anderen Farbe als bei einem aktiven Steuerelement angezeigt.|
|Vorschlag|Das vorherige Verhalten (.NET 4.0) kann wiederhergestellt werden, indem Sie die <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported>-Eigenschaft auf <code>false</code> festlegen.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|

