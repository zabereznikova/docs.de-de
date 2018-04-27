### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a>WPF-TextBox.Text wird möglicherweise nicht mehr mit der Datenbindung synchronisiert

|   |   |
|---|---|
|Details|In einigen Fällen stellt die <xref:System.Windows.Controls.TextBox.Text>-Eigenschaft einen früheren Wert des datengebundenen Eigenschaftswerts dar, wenn die Eigenschaft während eines Datenbindungsschreibvorgangs geändert wird.|
|Vorschlag|Dies sollte keine negativen Auswirkungen haben. Sie können jedoch das vorherige Verhalten wiederherstellen, indem Sie die <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty>-Eigenschaft auf <code>false</code> festlegen.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType></li></ul>|

