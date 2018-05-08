### <a name="binding-a-wpf-selector-property-such-as-selecteditem-to-a-static-property-does-not-work"></a>Das Binden einer WPF-Selektoreigenschaft (z.B. „SelectedItem“) an eine statische Eigenschaft funktioniert nicht

|   |   |
|---|---|
|Details|In .NET Framework 4.5 werden WPF-Selektoreigenschaften (z.B. &#39;SelectedItem&#39; auf <xref:System.Windows.Controls.ListBox?displayProperty=name> oder <xref:System.Windows.Controls.DataGrid?displayProperty=name>), die durch Daten an statische Eigenschaften gebunden sind, nicht ordnungsgemäß aktualisiert, wenn die gebundene Eigenschaft aktualisiert wird.|
|Vorschlag|Dieses Verhalten wurde in einem Wartungsupdate für .NET Framework 4.5 rückgängig gemacht. Aktualisieren Sie .NET Framework 4.5 oder führen Sie ein Upgrade auf .NET Framework 4.5.1 oder höher aus, um dieses Problem zu beheben.|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|

