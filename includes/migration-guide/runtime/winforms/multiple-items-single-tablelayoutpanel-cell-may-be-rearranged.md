### <a name="multiple-items-in-a-single-tablelayoutpanel-cell-may-be-rearranged"></a>Mehrere Elemente in einer einzelnen TableLayoutPanel-Zelle können neu angeordnet werden.

|   |   |
|---|---|
|Details|Wenn in .NET Framework 4.5 mehrere Elemente in derselben <xref:System.Windows.Forms.TableLayoutPanel?displayProperty=name>-Zelle platziert werden, können sie in einer anderen Reihenfolge als in .NET Framework 4.0 angezeigt werden.|
|Vorschlag|Dieses Verhalten wurde in einem Wartungsupdate für .NET Framework 4.5 rückgängig gemacht. Aktualisieren Sie .NET Framework 4.5 oder führen Sie ein Upgrade auf .NET Framework 4.5.1 oder höher aus, um dieses Problem zu beheben. Vermeiden Sie alternativ den mehrdeutigen Fall von mehreren Elementen in derselben <xref:System.Windows.Forms.TableLayoutPanel?displayProperty=name>-Zelle.|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.Forms.TableLayoutControlCollection.Add(System.Windows.Forms.Control%2CSystem.Int32%2CSystem.Int32)?displayProperty=nameWithType></li></ul>|
|Analyzer|<ul><li>CD0098</li></ul>|

