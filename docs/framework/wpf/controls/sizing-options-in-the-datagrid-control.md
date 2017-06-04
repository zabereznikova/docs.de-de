---
title: "Gr&#246;&#223;en&#228;nderungsoptionen im DataGrid-Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Automatische Größenanpassung von DataGrid"
  - "DataGrid-Steuerelement [WPF], Größe anpassen"
  - "Größe [WPF], DataGrid"
ms.assetid: 96a0e47e-b010-4302-98ef-2daac446d8db
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gr&#246;&#223;en&#228;nderungsoptionen im DataGrid-Steuerelement
Zum Steuern der Größenanpassung für das <xref:System.Windows.Controls.DataGrid> stehen verschiedene Optionen zur Verfügung.  Das <xref:System.Windows.Controls.DataGrid> sowie einzelne Zeilen und Spalten im <xref:System.Windows.Controls.DataGrid> können so festgelegt werden, dass deren Größe automatisch an den jeweiligen Inhalt angepasst wird, sie können aber auch auf bestimmte Werte festgelegt werden.  In der Standardeinstellung wird das <xref:System.Windows.Controls.DataGrid> je nach Größe des Inhalts vergrößert oder verkleinert.  
  
## Anpassen der Größe für ein DataGrid  
  
### Vorsichtsmaßnahmen beim Verwenden der automatischen Größenanpassung  
 Standardmäßig werden die <xref:System.Windows.FrameworkElement.Height%2A>\-Eigenschaft und die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft des <xref:System.Windows.Controls.DataGrid> auf <xref:System.Double.NaN?displayProperty=fullName> \("`Auto`" in XAML\) festgelegt, und die Größe des <xref:System.Windows.Controls.DataGrid> wird an die Größe des jeweiligen Inhalts angepasst.  
  
 Wenn ein <xref:System.Windows.Controls.DataGrid> in einem Container platziert wird, der die Größe der untergeordneten Elemente, z. B. eines <xref:System.Windows.Controls.Canvas> oder eines <xref:System.Windows.Controls.StackPanel>, nicht einschränkt, wird es über die sichtbaren Grenzen des Containers hinweg gestreckt, und es werden keine Bildlaufleisten angezeigt.  Diese Bedingung wirkt sich auf die Verwendbarkeit und auf die Leistung aus.  
  
 Wenn bei Bindung an ein Dataset die <xref:System.Windows.FrameworkElement.Height%2A> des <xref:System.Windows.Controls.DataGrid> nicht eingeschränkt wird, werden weiterhin Zeilen für jedes Datenelement im gebundenen Dataset hinzugefügt.  Auf diese Weise kann das <xref:System.Windows.Controls.DataGrid> beim Hinzufügen weiterer Zeilen über die sichtbaren Begrenzungen der Anwendung hinweg reichen.  Für das <xref:System.Windows.Controls.DataGrid> werden in diesem Fall keine Bildlaufleisten angezeigt, da dessen <xref:System.Windows.FrameworkElement.Height%2A> beim Hinzufügen neuer Zeilen weiterhin steigt.  
  
 Für jede Zeile im <xref:System.Windows.Controls.DataGrid> wird ein Objekt erstellt.  Wenn Sie mit einem umfangreichen Dataset arbeiten und die automatische Größenanpassung des <xref:System.Windows.Controls.DataGrid> zulassen, kann sich das Erstellen zahlreicher Objekte auf die Leistung der Anwendung auswirken.  
  
 Zur Vermeidung solcher Probleme wird bei der Arbeit mit umfangreichen Datasets empfohlen, die <xref:System.Windows.FrameworkElement.Height%2A> des <xref:System.Windows.Controls.DataGrid> explizit festzulegen oder dieses in einem Container zu platzieren, in dem dessen <xref:System.Windows.FrameworkElement.Height%2A> eingeschränkt wird, z. B. in einem <xref:System.Windows.Controls.Grid>.  Wenn die <xref:System.Windows.FrameworkElement.Height%2A> beschränkt wird, erstellt das <xref:System.Windows.Controls.DataGrid> nur die Zeilen, die in die angegebene <xref:System.Windows.FrameworkElement.Height%2A> passen, und verwendet diese Zeilen bei Bedarf wieder, um neue Daten anzuzeigen.  
  
### Festlegen der DataGrid\-Größe  
 Das <xref:System.Windows.Controls.DataGrid> kann so festgelegt werden, dass die Größe innerhalb angegebener Begrenzungen automatisch angepasst wird, das <xref:System.Windows.Controls.DataGrid> kann jedoch auch auf eine bestimmte Größe festgelegt werden.  In der folgenden Tabelle sind die Eigenschaften aufgeführt, mit denen die Größe des <xref:System.Windows.Controls.DataGrid> gesteuert werden kann.  
  
|Property|Beschreibung|  
|--------------|------------------|  
|<xref:System.Windows.FrameworkElement.Height%2A>|Legt eine bestimmte Höhe für das <xref:System.Windows.Controls.DataGrid> fest.|  
|<xref:System.Windows.FrameworkElement.MaxHeight%2A>|Legt die obere Begrenzung für die Höhe des <xref:System.Windows.Controls.DataGrid> fest.  Das <xref:System.Windows.Controls.DataGrid> wird vertikal vergrößert, bis es diese Höhe erreicht.|  
|<xref:System.Windows.FrameworkElement.MinHeight%2A>|Legt die untere Begrenzung für die Höhe des <xref:System.Windows.Controls.DataGrid> fest.  Das <xref:System.Windows.Controls.DataGrid> wird vertikal verkleinert, bis es diese Höhe erreicht.|  
|<xref:System.Windows.FrameworkElement.Width%2A>|Legt eine bestimmte Breite für das <xref:System.Windows.Controls.DataGrid> fest.|  
|<xref:System.Windows.FrameworkElement.MaxWidth%2A>|Legt die obere Begrenzung für die Breite des <xref:System.Windows.Controls.DataGrid> fest.  Das <xref:System.Windows.Controls.DataGrid> wird horizontal vergrößert, bis es diese Breite erreicht.|  
|<xref:System.Windows.FrameworkElement.MinWidth%2A>|Legt die untere Begrenzung für die Breite des <xref:System.Windows.Controls.DataGrid> fest.  Das <xref:System.Windows.Controls.DataGrid> wird horizontal verkleinert, bis es diese Breite erreicht.|  
  
## Größenanpassungen für Zeilen und Zeilenheader  
  
### DataGrid\-Zeilen  
 Standardmäßig wird die <xref:System.Windows.FrameworkElement.Height%2A>\-Eigenschaft einer <xref:System.Windows.Controls.DataGrid>\-Zeile auf <xref:System.Double.NaN?displayProperty=fullName> \("`Auto`" in XAML\) festgelegt, und die Zeilenhöhe wird auf die Größe des jeweiligen Inhalts vergrößert.  Die Höhe aller Zeilen im <xref:System.Windows.Controls.DataGrid> kann angegeben werden, indem die <xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=fullName>\-Eigenschaft festgelegt wird.  Benutzer können die Zeilenhöhe durch Ziehen der Zeilenüberschriftsteiler ändern.  
  
### DataGrid\-Zeilenheader  
 Wenn Zeilenheader angezeigt werden sollen, muss die <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A>\-Eigenschaft auf <xref:System.Windows.Controls.DataGridHeadersVisibility?displayProperty=fullName> oder <xref:System.Windows.Controls.DataGridHeadersVisibility?displayProperty=fullName> festgelegt werden.  Zeilenüberschriften werden standardmäßig angezeigt, und ihre Größe wird automatisch an den jeweiligen Inhalt angepasst.  Den Zeilenheadern kann eine bestimmte Breite zugewiesen werden, indem die <xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=fullName>\-Eigenschaft festgelegt wird.  
  
## Größenanpassungen für Spalten und Spaltenheader  
  
### DataGrid\-Spalten  
 Das <xref:System.Windows.Controls.DataGrid> verwendet Werte der <xref:System.Windows.Controls.DataGridLength>\-Struktur und der <xref:System.Windows.Controls.DataGridLengthUnitType>\-Struktur, um absolute oder automatische Größenanpassungsmodi anzugeben.  
  
 In der folgenden Tabelle werden die von der <xref:System.Windows.Controls.DataGridLengthUnitType>\-Struktur bereitgestellten Werte angezeigt.  
  
|Name|Beschreibung|  
|----------|------------------|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|Mit dem Standardmodus für automatische Größenanpassungen wird die Größe von <xref:System.Windows.Controls.DataGrid>\-Spalten anhand des Inhalts von Zellen und Spaltenheadern angepasst.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|Mit dem Modus für zellbasierte automatische Größenanpassungen wird die Größe von <xref:System.Windows.Controls.DataGrid>\-Spalten anhand des Inhalts von Zellen in der Spalte, nicht anhand von Spaltenheadern angepasst.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|Mit dem Modus für die headerbasierte automatische Größenanpassung wird die Größe von <xref:System.Windows.Controls.DataGrid>\-Spalten nur anhand des Inhalts von Spaltenheadern angepasst.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|Mit dem Modus für pixelbasierte Größenanpassungen werden <xref:System.Windows.Controls.DataGrid>\-Spalten anhand des bereitgestellten numerischen Werts angepasst.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType>|Der Modus für die Größenanpassung mit einer Sternvariablen wird verwendet, um den verfügbaren Platz nach gewichteten Proportionen zu verteilen.<br /><br /> In XAML werden Sternwerte als "n\*" ausgedrückt, wobei n einen numerischen Wert darstellt.  1\* ist gleichbedeutend mit \*.  Wenn z. B. zwei Spalten in einem <xref:System.Windows.Controls.DataGrid> Breiten von \* und 2\* aufweisen, erhält die erste Spalte einen Teil des verfügbaren Platzes, während der zweiten Spalte zwei Teile des verfügbaren Platzes zugewiesen werden.|  
  
 Mit der <xref:System.Windows.Controls.DataGridLengthConverter>\-Klasse können Sie Daten zwischen numerischen oder Zeichenfolgenwerten und <xref:System.Windows.Controls.DataGridLength>\-Werten konvertieren.  
  
 Standardmäßig ist die <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=fullName>\-Eigenschaft auf <xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A> und die <xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=fullName>\-Eigenschaft auf <xref:System.Windows.Controls.DataGridLength.Auto%2A> festgelegt.  Wenn der Größenanpassungsmodus auf <xref:System.Windows.Controls.DataGridLength.Auto%2A> oder <xref:System.Windows.Controls.DataGridLength.SizeToCells%2A> festgelegt ist, werden Spalten bis zur Breite ihres breitesten sichtbaren Inhalts vergrößert.  Bei Bildläufen bewirken diese Größenanpassungsmodi, dass Spalten vergrößert werden, wenn Inhalt, der die aktuelle Spaltengröße übersteigt, per Bildlauf sichtbar wird.  Wenn der Inhalt per Bildlauf aus dem sichtbaren Bereich entfernt wird, wird die Spalte nicht verkleinert.  
  
 Spalten im <xref:System.Windows.Controls.DataGrid> können auch so festgelegt werden, dass automatische Größenanpassungen nur innerhalb angegebener Begrenzungen vorgenommen werden. Spalten können aber auch auf eine bestimmte Größe festgelegt werden.  In der folgenden Tabelle sind die Eigenschaften aufgeführt, mit denen die Spaltengrößen gesteuert werden können.  
  
|Property|Beschreibung|  
|--------------|------------------|  
|<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=fullName>|Legt die Obergrenze für alle Spalten im <xref:System.Windows.Controls.DataGrid> fest.|  
|<xref:System.Windows.Controls.DataGridColumn.MaxWidth%2A?displayProperty=fullName>|Legt die Obergrenze für eine einzelne Spalte fest.  Überschreibt <xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=fullName>.|  
|<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=fullName>|Legt die Untergrenze für alle Spalten im <xref:System.Windows.Controls.DataGrid> fest.|  
|<xref:System.Windows.Controls.DataGridColumn.MinWidth%2A?displayProperty=fullName>|Legt die Untergrenze für eine einzelne Spalte fest.  Überschreibt <xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=fullName>.|  
|<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=fullName>|Legt für alle Spalten im <xref:System.Windows.Controls.DataGrid> eine bestimmte Breite fest.|  
|<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=fullName>|Legt für eine einzelne Spalte eine bestimmte Breite fest.  Überschreibt <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=fullName>.|  
  
### DataGrid\-Spaltenheader  
 Standardmäßig werden <xref:System.Windows.Controls.DataGrid>\-Spaltenheader angezeigt.  Wenn Spaltenheader ausgeblendet werden sollen, muss die <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A>\-Eigenschaft auf <xref:System.Windows.Controls.DataGridHeadersVisibility?displayProperty=fullName> oder <xref:System.Windows.Controls.DataGridHeadersVisibility?displayProperty=fullName> festgelegt werden.  Wenn Spaltenheader angezeigt werden, wird deren Größe in der Standardeinstellung automatisch an den jeweiligen Inhalt angepasst.  Den Spaltenheadern kann eine bestimmte Höhe zugewiesen werden, indem die <xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=fullName>\-Eigenschaft festgelegt wird.  
  
### Größenänderung mit der Maus  
 Benutzer können die Größe von Zeilen und Spalten im <xref:System.Windows.Controls.DataGrid> mithilfe der Zeilen\- oder Spaltenüberschriftsteiler ändern.  Das <xref:System.Windows.Controls.DataGrid> unterstützt auch die automatische Größenanpassung von Zeilen und Spalten per Doppelklick auf den Zeilen\- oder Spaltenüberschriftsteiler.  Wenn Sie verhindern möchten, dass ein Benutzer die Größe bestimmter Spalten ändert, legen Sie die <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=fullName>\-Eigenschaft für die betreffenden Spalten auf `false` fest.  Wenn Sie verhindern möchten, dass Benutzer die Größe aller Spalten ändern, legen Sie die <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=fullName>\-Eigenschaft auf `false` fest.  Wenn Sie verhindern möchten, dass Benutzer die Größe aller Zeilen ändern, legen Sie die <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=fullName>\-Eigenschaft auf `false` fest.  
  
## Siehe auch  
 <xref:System.Windows.Controls.DataGrid>   
 <xref:System.Windows.Controls.DataGridColumn>   
 <xref:System.Windows.Controls.DataGridLength>   
 <xref:System.Windows.Controls.DataGridLengthConverter>