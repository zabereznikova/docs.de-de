---
title: Größenänderungsoptionen im DataGrid-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid control [WPF], sizing
- size [WPF], DataGrid
- automatically size DataGrid [WPF]
ms.assetid: 96a0e47e-b010-4302-98ef-2daac446d8db
ms.openlocfilehash: 0019ac9ad82301506d2da279094b2c96e022e915
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557848"
---
# <a name="sizing-options-in-the-datagrid-control"></a>Größenänderungsoptionen im DataGrid-Steuerelement
Verschiedene Optionen stehen in Steuerelement wie die <xref:System.Windows.Controls.DataGrid> passt sich. Die <xref:System.Windows.Controls.DataGrid>, und einzelne Zeilen und Spalten in der <xref:System.Windows.Controls.DataGrid>, kann festgelegt werden, automatisch auf ihren Inhalt angepasst, oder auf bestimmte Werte festgelegt werden. Wird standardmäßig die <xref:System.Windows.Controls.DataGrid> vergrößern und verkleinern Sie die Größe seines Inhalts angepasst wird.  
  
## <a name="sizing-the-datagrid"></a>Ändern der Größe des DataGrid-Steuerelement  
  
### <a name="cautions-when-using-automatic-sizing"></a>Vorsichtsmaßnahmen bei Verwendung der automatischen Größenänderung  
 Wird standardmäßig die <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaften der <xref:System.Windows.Controls.DataGrid> festgelegt <xref:System.Double.NaN?displayProperty=nameWithType> ("`Auto`" in XAML), und die <xref:System.Windows.Controls.DataGrid> wird auf die Größe seines Inhalts angepasst.  
  
 Wenn in einem Container platziert werden, die nicht die Größe der untergeordneten Elemente, wie z. B. einschränkt eine <xref:System.Windows.Controls.Canvas> oder <xref:System.Windows.Controls.StackPanel>, die <xref:System.Windows.Controls.DataGrid> wird über die sichtbaren Grenzen des Containers gestreckt und Bildlaufleisten nicht angezeigt werden. Diese Bedingung hat Auswirkungen auf die benutzerfreundlichkeit und Qualität.  
  
 Wenn auf ein Dataset gebunden werden, wenn die <xref:System.Windows.FrameworkElement.Height%2A> von der <xref:System.Windows.Controls.DataGrid> ist nicht eingeschränkt wird, ist sie weiterhin eine Zeile für jedes Datenelement im gebundenen Dataset hinzugefügt. Dies kann dazu führen, dass die <xref:System.Windows.Controls.DataGrid> sichtbar außerhalb der Anwendung wächst, wenn Zeilen hinzugefügt werden. Die <xref:System.Windows.Controls.DataGrid> wird nicht angezeigt werden, Bildlaufleisten in diesem Fall weil seine <xref:System.Windows.FrameworkElement.Height%2A> weiterhin wachsen, um die neuen Zeilen aufzunehmen.  
  
 Ein Objekt wird erstellt für jede Zeile in der <xref:System.Windows.Controls.DataGrid>. Wenn Sie mit einer großen Datasets arbeiten und Sie können die <xref:System.Windows.Controls.DataGrid> selbst automatisch die Größe, kann die Erstellung einer großen Anzahl von Objekten die Leistung Ihrer Anwendung auswirken.  
  
 Um diese Probleme zu vermeiden, wenn Sie mit großen Datasets arbeiten, wird empfohlen, dass Sie ausdrücklich Festlegen der <xref:System.Windows.FrameworkElement.Height%2A> von der <xref:System.Windows.Controls.DataGrid> , oder platzieren Sie es in einem Container, die einschränken, seine <xref:System.Windows.FrameworkElement.Height%2A>, z. B. eine <xref:System.Windows.Controls.Grid>. Wenn die <xref:System.Windows.FrameworkElement.Height%2A> eingeschränkt, die <xref:System.Windows.Controls.DataGrid> erstellt nur die Zeilen, die innerhalb der angegebenen passen <xref:System.Windows.FrameworkElement.Height%2A>, und verwendet dann die Zeilen wieder nach Bedarf, um neue Daten anzuzeigen.  
  
### <a name="setting-the-datagrid-size"></a>Festlegen der DataGrid-Größe  
 Die <xref:System.Windows.Controls.DataGrid> kann festgelegt werden, um automatisch die Größe innerhalb der angegebenen Grenzen oder <xref:System.Windows.Controls.DataGrid> kann auf eine bestimmte Größe festgelegt werden. Die folgende Tabelle zeigt die Eigenschaften, die auf das Steuerelement festgelegt werden können die <xref:System.Windows.Controls.DataGrid> Größe.  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Windows.FrameworkElement.Height%2A>|Legt eine bestimmte Höhe für den <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.FrameworkElement.MaxHeight%2A>|Legt die Obergrenze für die Höhe der <xref:System.Windows.Controls.DataGrid>. Die <xref:System.Windows.Controls.DataGrid> wird vertikal vergrößert, bis es diese Höhe erreicht.|  
|<xref:System.Windows.FrameworkElement.MinHeight%2A>|Legt die untere Grenze für die Höhe der <xref:System.Windows.Controls.DataGrid>. Die <xref:System.Windows.Controls.DataGrid> wird vertikal verkleinern, bis diese Höhe erreicht.|  
|<xref:System.Windows.FrameworkElement.Width%2A>|Legt eine feste Breite für das <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.FrameworkElement.MaxWidth%2A>|Legt die Obergrenze für die Breite der <xref:System.Windows.Controls.DataGrid>. Die <xref:System.Windows.Controls.DataGrid> wird horizontal vergrößert, bis diese Breite erreicht.|  
|<xref:System.Windows.FrameworkElement.MinWidth%2A>|Legt die untere Grenze für die Breite der <xref:System.Windows.Controls.DataGrid>. Die <xref:System.Windows.Controls.DataGrid> wird horizontal verkleinern, bis diese Breite erreicht.|  
  
## <a name="sizing-rows-and-row-headers"></a>Größenanpassung von Zeilen und Zeilenheader  
  
### <a name="datagrid-rows"></a>DataGrid-Zeilen  
 Wird standardmäßig ein <xref:System.Windows.Controls.DataGrid> Zeile <xref:System.Windows.FrameworkElement.Height%2A> -Eigenschaftensatz auf <xref:System.Double.NaN?displayProperty=nameWithType> ("`Auto`" in XAML), und die Zeilenhöhe wird erweitert, um die Größe ihrer Inhalte. Die Höhe aller Zeilen in der <xref:System.Windows.Controls.DataGrid> können angegeben werden, indem die <xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=nameWithType> Eigenschaft. Benutzer können die Zeilenhöhe durch Ziehen der Zeile Header Trennblättern ändern.  
  
### <a name="datagrid-row-headers"></a>DataGrid-Zeilenheader  
 Anzuzeigende Zeilenüberschriften, die <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> Eigenschaft muss festgelegt werden, um <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> oder <xref:System.Windows.Controls.DataGridHeadersVisibility.All?displayProperty=nameWithType>. Standardmäßig Zeilenköpfe angezeigt werden, und sie Größe automatisch an ihren Inhalt angepasst. Die Zeilenköpfe können durch Festlegen eine bestimmte Breite weitergegeben werden die <xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=nameWithType> Eigenschaft.  
  
## <a name="sizing-columns-and-column-headers"></a>Größenanpassung von Spalten und Spaltenüberschriften  
  
### <a name="datagrid-columns"></a>DataGrid-Spalten  
 Die <xref:System.Windows.Controls.DataGrid> verwendet Werte von der <xref:System.Windows.Controls.DataGridLength> und <xref:System.Windows.Controls.DataGridLengthUnitType> Struktur absolute oder automatische Größenanpassungsmodi angeben.  
  
 Die folgende Tabelle zeigt die Werte gemäß der <xref:System.Windows.Controls.DataGridLengthUnitType> Struktur.  
  
|name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Auto>|Die Standardeinstellung automatische größenanpassung Modus Größen <xref:System.Windows.Controls.DataGrid> Spalten basierend auf den Inhalt von Zellen und Spaltenheader.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToCells>|Die Zelle-basierte automatische größenanpassung Modus Größen <xref:System.Windows.Controls.DataGrid> Spalten basierend auf den Inhalt der Zellen in der Spalte, z. B. nicht die Spaltenheader.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToHeader>|Die Header-basierte automatische größenanpassung Modus Größen <xref:System.Windows.Controls.DataGrid> Spalten basierend auf den Inhalt nur Spaltenheader.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Pixel>|Die Pixel-basierten Modus Größen Größe <xref:System.Windows.Controls.DataGrid> Spalten basierend auf den numerischen Wert bereitgestellt.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Star>|Der Stern Größenanpassungsmodus dient zum Verteilen der verfügbare Platz von gewichteten Proportionen.<br /><br /> In XAML werden Sternwerte als n * angegeben, wobei n für einen numerischen Wert darstellt. 1\* entspricht \*. Angenommen, zwei Spalten in einer <xref:System.Windows.Controls.DataGrid> Breiten von \* und 2\*, die erste Spalte erhält einen Teil des verfügbaren Platzes und die zweite Spalte erhielten zwei Teile des verfügbaren Speicherplatzes.|  
  
 Die <xref:System.Windows.Controls.DataGridLengthConverter> -Klasse kann verwendet werden, um Daten zwischen numerisch oder String-Werte zu konvertieren und <xref:System.Windows.Controls.DataGridLength> Werte.  
  
 Wird standardmäßig die <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType> -Eigenschaftensatz auf <xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A>, und die <xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType> -Eigenschaftensatz auf <xref:System.Windows.Controls.DataGridLength.Auto%2A>. Wenn der Größenanpassungsmodus auf festgelegt ist <xref:System.Windows.Controls.DataGridLength.Auto%2A> oder <xref:System.Windows.Controls.DataGridLength.SizeToCells%2A>, Spalten vergrößert, um die Breite des ihre breitesten sichtbaren Inhalt. Beim Durchführen eines Bildlaufs, bewirkt diese Größenanpassungsmodi, Spalten, wenn Inhalt, der größer als die aktuelle Spaltengröße einen Bildlauf angezeigt wird. Die Spalte wird nicht verkleinert werden, nachdem der Inhalt aus der Sicht Bildlauf durchgeführt wird.  
  
 Spalten in der <xref:System.Windows.Controls.DataGrid> kann auch festgelegt werden, um automatisch die Größe nur innerhalb der angegebenen Grenzen oder Spalten auf einer bestimmten Größe festgelegt werden können. Die folgende Tabelle zeigt die Eigenschaften, die zum Steuern der Spaltengröße festgelegt werden können.  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>|Legt die Obergrenze für alle Spalten in der <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.MaxWidth%2A?displayProperty=nameWithType>|Legt die Obergrenze für eine einzelne Spalte fest. Überschreibt <xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>|Legt die Untergrenze für alle Spalten in der <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.MinWidth%2A?displayProperty=nameWithType>|Legt fest, der die Untergrenze für eine einzelne Spalte. Überschreibt <xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>|Legt eine feste Breite für alle Spalten in der <xref:System.Windows.Controls.DataGrid>.|  
|<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType>|Legt eine feste Breite für eine einzelne Spalte fest. Überschreibt <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>.|  
  
### <a name="datagrid-column-headers"></a>DataGrid-Spaltenheader  
 Standardmäßig <xref:System.Windows.Controls.DataGrid> Spaltenüberschriften angezeigt werden. So blenden Sie die Spaltenüberschriften, aus der <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> Eigenschaft muss festgelegt werden, um <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> oder <xref:System.Windows.Controls.DataGridHeadersVisibility.None?displayProperty=nameWithType>. Standardmäßig wenn Spaltenüberschriften angezeigt werden, deren Größe automatisch an ihren Inhalt angepasst. Die Spaltenüberschriften können durch Festlegen eine bestimmte Höhe zugewiesen werden die <xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=nameWithType> Eigenschaft.  
  
### <a name="resizing-with-the-mouse"></a>Ändern der Größe, mit der Maus  
 Benutzer können die Größe <xref:System.Windows.Controls.DataGrid> Zeilen und Spalten durch Ziehen der Header Trennblättern Zeile oder Spalte. Die <xref:System.Windows.Controls.DataGrid> unterstützt auch die automatische größenanpassung von Zeilen und Spalten durch Doppelklicken auf den Unterteiler der Header Zeile oder Spalte. Um zu verhindern, dass einen Benutzer bestimmte Spalten Größenänderung, legen Sie die <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> Eigenschaft `false` für die einzelnen Spalten. Um zu verhindern, dass Benutzer die Größe aller Spalten ändern, legen Sie die <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> Eigenschaft `false`. Um zu verhindern, dass Benutzer die Größe aller Zeilen ändern, legen Sie die <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=nameWithType> Eigenschaft `false`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.DataGrid>  
 <xref:System.Windows.Controls.DataGridColumn>  
 <xref:System.Windows.Controls.DataGridLength>  
 <xref:System.Windows.Controls.DataGridLengthConverter>
