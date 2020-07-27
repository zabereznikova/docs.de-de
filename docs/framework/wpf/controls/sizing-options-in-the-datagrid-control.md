---
title: Größenänderungsoptionen im DataGrid-Steuerelement
description: Erfahren Sie, wie Sie einzelne Zeilen und Spalten im Windows Presentation Foundation DataGrid-Steuerelement so festlegen, dass die Größe auf ihren Inhalt oder bestimmte Werte zugeschnitten ist.
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid control [WPF], sizing
- size [WPF], DataGrid
- automatically size DataGrid [WPF]
ms.assetid: 96a0e47e-b010-4302-98ef-2daac446d8db
ms.openlocfilehash: 0f10e385cbf18a26989614363ca6cd9f92bc83ec
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164747"
---
# <a name="sizing-options-in-the-datagrid-control"></a>Größenänderungsoptionen im DataGrid-Steuerelement
Es stehen verschiedene Optionen zur Verfügung, um die <xref:System.Windows.Controls.DataGrid> Größe der Größen selbst zu steuern. Der <xref:System.Windows.Controls.DataGrid> und die einzelnen Zeilen und Spalten in der <xref:System.Windows.Controls.DataGrid> können auf die Größe automatisch auf ihren Inhalt festgelegt oder auf bestimmte Werte festgelegt werden. Standardmäßig <xref:System.Windows.Controls.DataGrid> wird vergrößert und verkleinert, um die Größe des Inhalts anzupassen.  
  
## <a name="sizing-the-datagrid"></a>Größe des DataGrid-Steuerelement  
  
### <a name="cautions-when-using-automatic-sizing"></a>Warnungen bei Verwendung der automatischen Größenanpassung  
 Standardmäßig werden die <xref:System.Windows.FrameworkElement.Height%2A> -Eigenschaft und die-Eigenschaft <xref:System.Windows.FrameworkElement.Width%2A> von <xref:System.Windows.Controls.DataGrid> auf <xref:System.Double.NaN?displayProperty=nameWithType> (" `Auto` " in XAML) festgelegt, und der <xref:System.Windows.Controls.DataGrid> wird an die Größe des Inhalts angepasst.  
  
 Wenn Sie in einem Container platziert werden, der die Größe der untergeordneten Elemente nicht einschränkt (z. b. <xref:System.Windows.Controls.Canvas> oder) <xref:System.Windows.Controls.StackPanel> , <xref:System.Windows.Controls.DataGrid> wird der über die sichtbaren Begrenzungen des Containers hinaus gestreckt, und Scrollleisten werden nicht angezeigt. Diese Bedingung hat sowohl Nutzbarkeit als auch Leistungs Auswirkungen.  
  
 Wenn das der an ein DataSet gebunden <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.Controls.DataGrid> ist, wird für jedes Datenelement im gebundenen Dataset weiterhin eine Zeile hinzugefügt. Dies kann bewirken, dass der <xref:System.Windows.Controls.DataGrid> außerhalb der sichtbaren Grenzen ihrer Anwendung wächst, wenn Zeilen hinzugefügt werden. <xref:System.Windows.Controls.DataGrid>In wird in diesem Fall keine Scrollleisten angezeigt, da der <xref:System.Windows.FrameworkElement.Height%2A> fortlaufend vergrößert wird, um die neuen Zeilen zu unterstützen.  
  
 Ein-Objekt wird für jede Zeile in der erstellt <xref:System.Windows.Controls.DataGrid> . Wenn Sie mit einem großen Dataset arbeiten und die <xref:System.Windows.Controls.DataGrid> Automatische Größe von selbst zulassen, wirkt sich die Erstellung einer großen Anzahl von Objekten möglicherweise auf die Leistung der Anwendung aus.  
  
 Um diese Probleme zu vermeiden, wenn Sie mit großen Datasets arbeiten, empfiehlt es sich, die von explizit festzulegen <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.Controls.DataGrid> oder Sie in einem Container zu platzieren, der die-Einschränkung einschränkt <xref:System.Windows.FrameworkElement.Height%2A> , z <xref:System.Windows.Controls.Grid> . b.. Wenn <xref:System.Windows.FrameworkElement.Height%2A> eingeschränkt ist, <xref:System.Windows.Controls.DataGrid> werden von nur die Zeilen erstellt, die in den angegebenen passen <xref:System.Windows.FrameworkElement.Height%2A> , und diese Zeilen werden nach Bedarf wieder verwendet, um neue Daten anzuzeigen.  
  
### <a name="setting-the-datagrid-size"></a>Festlegen der DataGrid-Größe  
 <xref:System.Windows.Controls.DataGrid>Kann festgelegt werden, um eine automatische Größe innerhalb der angegebenen Begrenzungen festzulegen, oder <xref:System.Windows.Controls.DataGrid> kann auf eine bestimmte Größe festgelegt werden. In der folgenden Tabelle sind die Eigenschaften aufgeführt, die festgelegt werden können, um die Größe zu steuern <xref:System.Windows.Controls.DataGrid> .  
  
|Eigenschaft|BESCHREIBUNG|  
|--------------|-----------------|  
|<xref:System.Windows.FrameworkElement.Height%2A>|Legt eine bestimmte Höhe für den fest <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.FrameworkElement.MaxHeight%2A>|Legt die obere Grenze für die Höhe des fest <xref:System.Windows.Controls.DataGrid> . Die <xref:System.Windows.Controls.DataGrid> vergrößert sich vertikal, bis Sie diese Höhe erreicht.|  
|<xref:System.Windows.FrameworkElement.MinHeight%2A>|Legt die untere Grenze für die Höhe des fest <xref:System.Windows.Controls.DataGrid> . Der <xref:System.Windows.Controls.DataGrid> verkleinert sich vertikal, bis er diese Höhe erreicht.|  
|<xref:System.Windows.FrameworkElement.Width%2A>|Legt eine bestimmte Breite für den fest <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.FrameworkElement.MaxWidth%2A>|Legt die obere Grenze für die Breite des fest <xref:System.Windows.Controls.DataGrid> . Die <xref:System.Windows.Controls.DataGrid> vergrößert sich horizontal, bis Sie diese Breite erreicht.|  
|<xref:System.Windows.FrameworkElement.MinWidth%2A>|Legt die untere Grenze für die Breite des fest <xref:System.Windows.Controls.DataGrid> . Der <xref:System.Windows.Controls.DataGrid> verkleinert sich horizontal, bis diese Breite erreicht ist.|  
  
## <a name="sizing-rows-and-row-headers"></a>Größenanpassung von Zeilen und Zeilen Headern  
  
### <a name="datagrid-rows"></a>DataGrid-Zeilen  
 Standardmäßig ist die <xref:System.Windows.Controls.DataGrid> -Eigenschaft einer Zeile <xref:System.Windows.FrameworkElement.Height%2A> auf <xref:System.Double.NaN?displayProperty=nameWithType> (" `Auto` " in XAML) festgelegt, und die Zeilenhöhe wird auf die Größe Ihrer Inhalte erweitert. Die Höhe aller Zeilen im <xref:System.Windows.Controls.DataGrid> kann durch Festlegen der-Eigenschaft angegeben werden <xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=nameWithType> . Benutzer können die Zeilenhöhe durchziehen der Zeilen Header Divider ändern.  
  
### <a name="datagrid-row-headers"></a>DataGrid-Zeilen Header  
 Zum Anzeigen von Zeilen Headern <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> muss die-Eigenschaft auf oder festgelegt werden <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> <xref:System.Windows.Controls.DataGridHeadersVisibility.All?displayProperty=nameWithType> . Standardmäßig werden Zeilen Header angezeigt, und Sie werden automatisch an ihren Inhalt angepasst. Die Zeilen Kopfzeilen können durch Festlegen der-Eigenschaft eine bestimmte Breite erhalten <xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=nameWithType> .  
  
## <a name="sizing-columns-and-column-headers"></a>Größenänderung von Spalten und Spaltenüberschriften  
  
### <a name="datagrid-columns"></a>DataGrid-Spalten  
 Der <xref:System.Windows.Controls.DataGrid> verwendet die Werte der <xref:System.Windows.Controls.DataGridLength> -Struktur und der- <xref:System.Windows.Controls.DataGridLengthUnitType> Struktur, um den absoluten oder automatischen Größen Anpassungsmodus anzugeben.  
  
 Die folgende Tabelle zeigt die Werte, die von der-Struktur bereitgestellt werden <xref:System.Windows.Controls.DataGridLengthUnitType> .  
  
|Name|BESCHREIBUNG|  
|----------|-----------------|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Auto>|Der Standardmodus für die automatische Größenanpassung <xref:System.Windows.Controls.DataGrid> basiert auf dem Inhalt von Zellen und Spalten Headern.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToCells>|Der Zellen basierte Modus für die automatische Größenanpassung <xref:System.Windows.Controls.DataGrid> basiert auf dem Inhalt der Zellen in der Spalte, nicht einschließlich der Spaltenüberschriften.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToHeader>|Der Header basierte Modus für die automatische Größenanpassung <xref:System.Windows.Controls.DataGrid> basiert auf dem Inhalt von Spalten Headern.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Pixel>|Der pixelbasierte Größen Anpassungsmodus gibt <xref:System.Windows.Controls.DataGrid> Spalten basierend auf dem bereitgestellten numerischen Wert an.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Star>|Der Stern Größen Modus wird verwendet, um den verfügbaren Speicherplatz durch gewichtete Proportionen zu verteilen.<br /><br /> In XAML werden Stern Werte als n * ausgedrückt, wobei n einen numerischen Wert darstellt. 1 \* entspricht \* . Wenn z. b. zwei Spalten in einer über die <xref:System.Windows.Controls.DataGrid> breiten \* und 2 \* verfügen, würde die erste Spalte einen Teil des verfügbaren Speicherplatzes erhalten, und die zweite Spalte würde zwei Teile des verfügbaren Speicherplatzes erhalten.|  
  
 Die <xref:System.Windows.Controls.DataGridLengthConverter> -Klasse kann verwendet werden, um Daten zwischen numerischen Werten oder Zeichen folgen Werten und-Werten zu konvertieren <xref:System.Windows.Controls.DataGridLength> .  
  
 Standardmäßig ist die <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType> -Eigenschaft auf festgelegt <xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A> , und die- <xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType> Eigenschaft ist auf festgelegt <xref:System.Windows.Controls.DataGridLength.Auto%2A> . Wenn der Größen Anpassungsmodus auf oder festgelegt ist <xref:System.Windows.Controls.DataGridLength.Auto%2A> <xref:System.Windows.Controls.DataGridLength.SizeToCells%2A> , werden die Spalten auf die Breite des breitesten sichtbaren Inhalts vergrößert. Beim Scrollen bewirken diese Größen Anpassungs Modi, dass Spalten erweitert werden, wenn der Inhalt, der größer als die aktuelle Spaltengröße ist, in die Ansicht gescrollt wird. Die Spalte wird nicht verkleinert, nachdem der Inhalt aus der Ansicht ausgescrollt wurde.  
  
 Spalten in <xref:System.Windows.Controls.DataGrid> können auch so festgelegt werden, dass Sie nur innerhalb der angegebenen Grenzen automatisch Größe aufweisen, oder für Spalten kann eine bestimmte Größe festgelegt werden. In der folgenden Tabelle sind die Eigenschaften aufgeführt, die zum Steuern von Spaltengrößen festgelegt werden können.  
  
|Eigenschaft|BESCHREIBUNG|  
|--------------|-----------------|  
|<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>|Legt die obere Grenze für alle Spalten im fest <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.Controls.DataGridColumn.MaxWidth%2A?displayProperty=nameWithType>|Legt die obere Grenze für eine einzelne Spalte fest. Überschreibt <xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>|Legt die untere Grenze für alle Spalten im fest <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.Controls.DataGridColumn.MinWidth%2A?displayProperty=nameWithType>|Legt die untere Grenze für eine einzelne Spalte fest. Überschreibt <xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>.|  
|<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>|Legt eine bestimmte Breite für alle Spalten im fest <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType>|Legt eine bestimmte Breite für eine einzelne Spalte fest. Überschreibt <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>.|  
  
### <a name="datagrid-column-headers"></a>DataGrid-Spaltenüberschriften  
 Standardmäßig <xref:System.Windows.Controls.DataGrid> werden Spaltenüberschriften angezeigt. Um Spaltenüberschriften auszublenden, muss die- <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> Eigenschaft auf oder festgelegt werden <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> <xref:System.Windows.Controls.DataGridHeadersVisibility.None?displayProperty=nameWithType> . Wenn Spaltenüberschriften angezeigt werden, werden Sie standardmäßig automatisch an ihren Inhalt angepasst. Die Spaltenüberschriften können durch Festlegen der-Eigenschaft eine bestimmte Höhe erhalten <xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=nameWithType> .  
  
### <a name="resizing-with-the-mouse"></a>Ändern der Größe mit der Maus  
 Benutzer können die Größe <xref:System.Windows.Controls.DataGrid> von Zeilen und Spalten ändern, indem Sie die Zeilen-oder Spaltenheader unter Teiler ziehen. <xref:System.Windows.Controls.DataGrid>Unterstützt auch die automatische Größe von Zeilen und Spalten, indem auf den Zeilen-oder Spaltenheader unter Teiler Doppel geklickt wird. Um zu verhindern, dass ein Benutzer die Größe bestimmter Spalten ändert, legen Sie die- <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> Eigenschaft `false` für die einzelnen Spalten auf fest. Um zu verhindern, dass Benutzer die Größe aller Spalten ändern, legen Sie die- <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> Eigenschaft auf fest `false` . Legen Sie die-Eigenschaft auf fest, um zu verhindern, dass Benutzer die Größe aller Zeilen ändern <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=nameWithType> `false` .  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.DataGrid>
- <xref:System.Windows.Controls.DataGridColumn>
- <xref:System.Windows.Controls.DataGridLength>
- <xref:System.Windows.Controls.DataGridLengthConverter>
