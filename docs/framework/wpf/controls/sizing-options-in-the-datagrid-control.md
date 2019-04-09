---
title: Größenänderungsoptionen im DataGrid-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid control [WPF], sizing
- size [WPF], DataGrid
- automatically size DataGrid [WPF]
ms.assetid: 96a0e47e-b010-4302-98ef-2daac446d8db
ms.openlocfilehash: 6d100fb17b1ee3e652985a637d333d9f65e20d36
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219199"
---
# <a name="sizing-options-in-the-datagrid-control"></a>Größenänderungsoptionen im DataGrid-Steuerelement
Verschiedene Optionen zur Verfügung, um zu steuern wie die <xref:System.Windows.Controls.DataGrid> wird die Größe. Die <xref:System.Windows.Controls.DataGrid>, und einzelne Zeilen und Spalten in der <xref:System.Windows.Controls.DataGrid>, auf die Größe automatisch an den jeweiligen Inhalt festgelegt werden kann, oder auf bestimmte Werte festgelegt werden kann. In der Standardeinstellung die <xref:System.Windows.Controls.DataGrid> vergrößert oder verkleinert werden, um die Größe seines Inhalts angepasst.  
  
## <a name="sizing-the-datagrid"></a>Größenanpassung von DataGrid  
  
### <a name="cautions-when-using-automatic-sizing"></a>Vorsichtsmaßnahmen bei Verwendung der automatischen Größenanpassung  
 In der Standardeinstellung die <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaften der <xref:System.Windows.Controls.DataGrid> festgelegt <xref:System.Double.NaN?displayProperty=nameWithType> ("`Auto`" in XAML), und die <xref:System.Windows.Controls.DataGrid> wird auf die Größe seines Inhalts angepasst.  
  
 Wenn in einem Container platziert werden, die nicht die Größe der untergeordneten Elemente, wie z. B. einschränkt eine <xref:System.Windows.Controls.Canvas> oder <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.DataGrid> wird gestreckt, über den sichtbaren Bereich des Containers und keine Bildlaufleisten angezeigt werden. Dies hat Auswirkungen auf die Nutzbarkeit und Leistung.  
  
 Wenn auf ein Dataset gebunden sind, wenn die <xref:System.Windows.FrameworkElement.Height%2A> von der <xref:System.Windows.Controls.DataGrid> ist nicht eingeschränkt wird, ist sie weiterhin eine Zeile für jedes Datenelement im gebundenen Dataset hinzuzufügen. Dies kann dazu führen, dass die <xref:System.Windows.Controls.DataGrid> sichtbar außerhalb der Anwendung wächst, wenn Zeilen hinzugefügt werden. Die <xref:System.Windows.Controls.DataGrid> wird nicht angezeigt, Bildlaufleisten in diesem Fall weil seine <xref:System.Windows.FrameworkElement.Height%2A> weiterhin wachsen, um die neuen Zeilen aufzunehmen.  
  
 Ein Objekt erstellt wird, für jede Zeile in der <xref:System.Windows.Controls.DataGrid>. Wenn Sie mit einem großen Dataset arbeiten und Sie können die <xref:System.Windows.Controls.DataGrid> um automatisch seine Größe selbst festlegen, kann die Erstellung einer großen Anzahl von Objekten auf die Leistung Ihrer Anwendung auswirken.  
  
 Um diese Probleme zu vermeiden, wenn Sie mit großen Datasets arbeiten, wird empfohlen, dass Sie ausdrücklich Festlegen der <xref:System.Windows.FrameworkElement.Height%2A> von der <xref:System.Windows.Controls.DataGrid> , oder platzieren Sie es in einem Container, mit denen eingeschränkt wird, wird die <xref:System.Windows.FrameworkElement.Height%2A>, wie z. B. eine <xref:System.Windows.Controls.Grid>. Wenn die <xref:System.Windows.FrameworkElement.Height%2A> eingeschränkt, die <xref:System.Windows.Controls.DataGrid> erstellt nur die Zeilen, die in der angegebenen passen <xref:System.Windows.FrameworkElement.Height%2A>, und verwendet dann die Zeilen wieder nach Bedarf, um neue Daten anzuzeigen.  
  
### <a name="setting-the-datagrid-size"></a>Festlegen der DataGrid-Größe  
 Die <xref:System.Windows.Controls.DataGrid> kann festgelegt werden, automatisch die Größe innerhalb der angegebenen Grenzen oder die <xref:System.Windows.Controls.DataGrid> kann auf eine bestimmte Größe festgelegt werden. Die folgende Tabelle zeigt die Eigenschaften, die auf das Steuerelement festgelegt werden können die <xref:System.Windows.Controls.DataGrid> Größe.  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Windows.FrameworkElement.Height%2A>|Legt eine bestimmte Höhe für den <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.FrameworkElement.MaxHeight%2A>|Legt die Obergrenze für die Höhe der <xref:System.Windows.Controls.DataGrid>. Die <xref:System.Windows.Controls.DataGrid> vertikal vergrößert werden, bis es diese Höhe erreicht.|  
|<xref:System.Windows.FrameworkElement.MinHeight%2A>|Legt die untere Grenze für die Höhe der <xref:System.Windows.Controls.DataGrid>. Die <xref:System.Windows.Controls.DataGrid> wird vertikal verkleinern, bis es diese Höhe erreicht.|  
|<xref:System.Windows.FrameworkElement.Width%2A>|Legt eine feste Breite für die <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.FrameworkElement.MaxWidth%2A>|Legt die Obergrenze für die Breite der <xref:System.Windows.Controls.DataGrid>. Die <xref:System.Windows.Controls.DataGrid> horizontal vergrößert werden, bis es diese Breite erreicht.|  
|<xref:System.Windows.FrameworkElement.MinWidth%2A>|Legt die untere Grenze für die Breite der <xref:System.Windows.Controls.DataGrid>. Die <xref:System.Windows.Controls.DataGrid> wird horizontal verkleinern, bis diese Breite erreicht.|  
  
## <a name="sizing-rows-and-row-headers"></a>Größenanpassung von Zeilen und Zeilenüberschriften  
  
### <a name="datagrid-rows"></a>DataGrid-Zeilen  
 Standardmäßig eine <xref:System.Windows.Controls.DataGrid> Zeile <xref:System.Windows.FrameworkElement.Height%2A> -Eigenschaftensatz auf <xref:System.Double.NaN?displayProperty=nameWithType> ("`Auto`" in XAML), und die Zeilenhöhe wird erweitert, um die Größe des Inhalts. Die Höhe aller Zeilen in der <xref:System.Windows.Controls.DataGrid> kann angegeben werden, durch Festlegen der <xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=nameWithType> Eigenschaft. Benutzer können die Zeilenhöhe durch Ziehen der Unterteiler mit Kopfzeile ändern.  
  
### <a name="datagrid-row-headers"></a>DataGrid-Zeilenheader  
 Zum Anzeigen von Zeilenköpfen der <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> Eigenschaft muss festgelegt werden, um <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> oder <xref:System.Windows.Controls.DataGridHeadersVisibility.All?displayProperty=nameWithType>. In der Standardeinstellung Zeilenüberschriften angezeigt werden, und sie Größe automatisch an ihren Inhalt angepasst. Die Zeilenüberschriften können eine bestimmte Breite zugewiesen werden, durch Festlegen der <xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=nameWithType> Eigenschaft.  
  
## <a name="sizing-columns-and-column-headers"></a>Größenanpassung von Spalten und Spaltenheader  
  
### <a name="datagrid-columns"></a>DataGrid-Spalten  
 Die <xref:System.Windows.Controls.DataGrid> verwendet Werte von der <xref:System.Windows.Controls.DataGridLength> und <xref:System.Windows.Controls.DataGridLengthUnitType> -Struktur in absoluten oder automatische Größenanpassungsmodi angeben.  
  
 Die folgende Tabelle zeigt die Beispielwerte durch die <xref:System.Windows.Controls.DataGridLengthUnitType> Struktur.  
  
|Name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Auto>|Die Standardeinstellung automatische größenanpassung Modus Größen <xref:System.Windows.Controls.DataGrid> basierend auf den Inhalt von Zellen und Spaltenheader.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToCells>|Die zellenbasierte automatische größenanpassung Modus Größen <xref:System.Windows.Controls.DataGrid> basierend auf den Inhalt der Zellen in der Spalte, die Spaltenheader nicht eingeschlossen.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToHeader>|Die Header-basierte automatische größenanpassung Modus Größen <xref:System.Windows.Controls.DataGrid> basierend auf den Inhalt der nur die Spaltenüberschriften.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Pixel>|Die Pixel-basierten Modus Größen größenanpassung <xref:System.Windows.Controls.DataGrid> basierend auf den numerischen Wert zur Verfügung gestellt.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Star>|Der sternvariabler-Modus wird von gewichteten Proportionen verwendet, um Speicherplatz zu verteilen.<br /><br /> In XAML werden die Sternwerte als n * ausgedrückt, wobei n für einen numerischen Wert darstellt. 1\* entspricht \*. Angenommen, zwei Spalten in einer <xref:System.Windows.Controls.DataGrid> Breiten von \* und 2\*, die erste Spalte erhält einen Teil des verfügbaren Speicherplatzes und die zweite Spalte zwei Teile der verfügbare Platz erhält.|  
  
 Die <xref:System.Windows.Controls.DataGridLengthConverter> Klasse kann verwendet werden, um Daten zwischen numerisch oder String-Werte zu konvertieren und <xref:System.Windows.Controls.DataGridLength> Werte.  
  
 In der Standardeinstellung die <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType> -Eigenschaftensatz auf <xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A>, und die <xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType> -Eigenschaftensatz auf <xref:System.Windows.Controls.DataGridLength.Auto%2A>. Wenn Sie den Größenanpassungsmodus auf festgelegt ist <xref:System.Windows.Controls.DataGridLength.Auto%2A> oder <xref:System.Windows.Controls.DataGridLength.SizeToCells%2A>, Spalten vergrößert, um die Breite des ihres breitesten sichtbaren Inhalts. Beim Durchführen eines Bildlaufs, verursacht diese Größenanpassungsmodi Spalten aus, wenn der Inhalt zu erweitern, die größer als die aktuelle Spaltengröße in die Ansicht gescrollt wird. Die Spalte wird nicht verkleinert werden, nachdem der Inhalt ein Bildlauf nicht aus der Sicht durchgeführt wird.  
  
 Spalten in der <xref:System.Windows.Controls.DataGrid> kann auch festgelegt werden, automatisch die Größe nur innerhalb der angegebenen Grenzen und können auf eine bestimmte Größe festgelegt werden. Die folgende Tabelle zeigt die Eigenschaften, die zum Steuern der Spaltengröße festgelegt werden können.  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>|Legt die Obergrenze für alle Spalten in der <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.MaxWidth%2A?displayProperty=nameWithType>|Legt fest, der die Obergrenze für eine einzelne Spalte. Überschreibt <xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>|Legt die Untergrenze für alle Spalten in der <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.MinWidth%2A?displayProperty=nameWithType>|Legt fest, der die Untergrenze für eine einzelne Spalte. Überschreibt <xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>|Legt eine bestimmte Breite für alle Spalten in der <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType>|Legt eine bestimmte Breite für eine einzelne Spalte fest. Überschreibt <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>.|  
  
### <a name="datagrid-column-headers"></a>DataGrid-Spaltenheader  
 In der Standardeinstellung <xref:System.Windows.Controls.DataGrid> Spaltenüberschriften angezeigt werden. So blenden Sie Spaltenüberschriften aus der <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> Eigenschaft muss festgelegt werden, um <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> oder <xref:System.Windows.Controls.DataGridHeadersVisibility.None?displayProperty=nameWithType>. Standard Wenn Spaltenheader angezeigt werden, deren Größe automatisch an ihren Inhalt angepasst. Die Spaltenüberschriften können eine bestimmte Höhe zugewiesen werden, durch Festlegen der <xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=nameWithType> Eigenschaft.  
  
### <a name="resizing-with-the-mouse"></a>Ändern der Größe, mit der Maus  
 Benutzer können die Größe <xref:System.Windows.Controls.DataGrid> Zeilen und Spalten durch Ziehen der Headerunterteiler Zeile oder Spalte. Die <xref:System.Windows.Controls.DataGrid> unterstützt auch das automatische Ändern der Größe von Zeilen und Spalten durch Doppelklicken auf die Zeile oder Spalte Headerunterteiler. Um zu verhindern, dass einen Benutzer bestimmte Spalten Größe, legen Sie die <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> Eigenschaft `false` für einzelnen Spalten. Um zu verhindern, dass Benutzer die Größe aller Spalten ändern, legen Sie die <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> Eigenschaft `false`. Um zu verhindern, dass Benutzer die Größe aller Zeilen ändern, legen Sie die <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=nameWithType> Eigenschaft `false`.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.DataGrid>
- <xref:System.Windows.Controls.DataGridColumn>
- <xref:System.Windows.Controls.DataGridLength>
- <xref:System.Windows.Controls.DataGridLengthConverter>
