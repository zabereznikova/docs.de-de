---
title: 'Optimieren der Leistung: Steuerelemente'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], improving performance
- container recycling [WPF]
- user interface virtualization [WPF]
ms.assetid: 45a31c43-ea8a-4546-96c8-0631b9934179
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b8008d104437454f36f6f425634c40968d5481a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="optimizing-performance-controls"></a>Optimieren der Leistung: Steuerelemente
In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stehen viele gängige Benutzeroberflächenkomponenten zur Verfügung, die in den meisten Windows Anwendungen verwendet werden. In diesem Thema werden Techniken dargestellt, mit denen Sie die Leistung Ihrer Benutzeroberfläche (UI) optimieren können.  
  
 
  
<a name="Displaying"></a>   
## <a name="displaying-large-data-sets"></a>Anzeigen von großen Datasets  
 WPF-Steuerelemente, z. B. die <xref:System.Windows.Controls.ListView> und <xref:System.Windows.Controls.ComboBox> werden verwendet, um Listen von Elementen in einer Anwendung anzeigen. Wenn die anzuzeigende Liste sehr groß ist, kann dies die Leistung der Anwendung beeinträchtigen. Dies liegt daran, dass das Standardlayoutsystem einen Layoutcontainer für jedes mit dem Listensteuerelement verknüpfte Element erstellt und dessen Layoutgröße und -position berechnet. Für gewöhnlich müssen Sie nicht alle Elemente gleichzeitig anzeigen; stattdessen zeigen Sie eine Teilmenge an, und der Benutzer scrollt durch die Liste. In diesem Fall macht es Sinn, die UI-*Virtualisierung* zu verwenden; dies bedeutet, dass die Generierung eines Elementcontainers und die damit verknüpfte Layoutberechnung verzögert werden, bis das Element sichtbar ist.  
  
 Die UI-Virtualisierung ist ein wichtiger Aspekt der Listensteuerelemente. Die UI-Virtualisierung ist nicht mit der Datenvirtualisierung zu verwechseln. Bei der UI-Virtualisierung werden nur sichtbare Elemente im Speicher gespeichert; in einem Datenbindungsszenario wird die gesamte Datenstruktur im Speicher gespeichert. Im Gegensatz dazu werden bei der Datenvisualisierung nur die Datenelemente gespeichert, die auf dem Bildschirm im Speicher sichtbar sind.  
  
 Standardmäßig ist die Virtualisierung der Benutzeroberfläche aktiviert, für die <xref:System.Windows.Controls.ListView> und <xref:System.Windows.Controls.ListBox> steuert, wann die Listenelemente an Daten gebunden sind. <xref:System.Windows.Controls.TreeView>Virtualisierung kann aktiviert werden, durch Festlegen der <!--zz <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=nameWithType> --> `IsVirtualizing` angefügten Eigenschaft, um `true`. Die Virtualisierung der Benutzeroberfläche für benutzerdefinierte Steuerelemente zu ermöglichen, die abgeleitet werden sollen <xref:System.Windows.Controls.ItemsControl> oder bereits vorhandene Steuerelemente verwendet werden, die <xref:System.Windows.Controls.StackPanel> Klasse, z. B. <xref:System.Windows.Controls.ComboBox>, können Sie festlegen, der <xref:System.Windows.Controls.ItemsControl.ItemsPanel%2A> zu <xref:System.Windows.Controls.VirtualizingStackPanel> und legen Sie <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizing%2A> zu `true`. Allerdings kann es passieren, dass Sie die UI-Virtualisierung für diese Steuerelemente deaktivieren, ohne es zu merken. Durch folgende Bedingungen kann die UI-Virtualisierung deaktiviert werden:  
  
-   Elementcontainer hinzukommen direkt an die <xref:System.Windows.Controls.ItemsControl>. Z. B. wenn eine Anwendung explizit hinzufügt, <xref:System.Windows.Controls.ListBoxItem> Datenbankobjekte in einer <xref:System.Windows.Controls.ListBox>, die <xref:System.Windows.Controls.ListBox> ist nicht virtualisiert werden. die <xref:System.Windows.Controls.ListBoxItem> Objekte.  
  
-   Die Elementcontainer in der <xref:System.Windows.Controls.ItemsControl> weisen unterschiedliche Datentypen. Z. B. eine <xref:System.Windows.Controls.Menu> , verwendet <xref:System.Windows.Controls.Separator> -Objekte können nicht implementieren Element wiederverwendet werden, da die <xref:System.Windows.Controls.Menu> enthält Objekte vom Typ <xref:System.Windows.Controls.Separator> und <xref:System.Windows.Controls.MenuItem>.  
  
-   Festlegen von <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> auf `false`.  
  
-   Festlegen von <!--zz <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A>--> `IsVirtualizing` auf `false`.  
  
 Bei der Virtualisierung von Elementcontainern ist es maßgeblich, zu wissen, ob Ihnen Informationen bezüglich des zusätzlichen Zustands des Elementcontainers vorliegen, der zu dem Element gehört. Falls dem so ist, müssen Sie den zusätzlichen Zustand speichern. Angenommen, Sie müssen möglicherweise Elements in ein <xref:System.Windows.Controls.Expander> Steuerelement und dem <xref:System.Windows.Controls.Expander.IsExpanded%2A> Status gebunden ist, auf das Element Container, und nicht auf das Element selbst. Wenn der Container wiederverwendet wird, für das neue Element, den aktuellen Wert der <xref:System.Windows.Controls.Expander.IsExpanded%2A> für das neue Element verwendet wird. Außerdem verliert das alte Element den richtigen <xref:System.Windows.Controls.Expander.IsExpanded%2A> Wert.  
  
 Im Moment gibt es keine WPF-Steuerelemente, die integrierte Unterstützung für die Datenvirtualisierung bieten.  
  
<a name="Container"></a>   
## <a name="container-recycling"></a>Wiederverwenden von Containern  
 Eine Optimierung für die Virtualisierung der Benutzeroberfläche hinzugefügt, die in .NET Framework 3.5 SP1 für Steuerelemente, die von erben <xref:System.Windows.Controls.ItemsControl> ist *recycling Container* können die Durchführen eines Bildlaufs Leistung auch verbessern.  Wenn ein <xref:System.Windows.Controls.ItemsControl> , verwendet die Virtualisierung der Benutzeroberfläche aufgefüllt wird, wird einen Elementcontainer für jedes Element, das Bildlauf sichtbar und zerstört der Elementcontainer für jedes Element, das aus der Sicht verschiebt erstellt. *Container Wiederverwendung* aktiviert das Steuerelement für unterschiedliche Datenelemente, die vorhandenen Elementcontainer wiederverwenden, sodass Elementcontainer nicht ständig erstellt und werden, als der Benutzer einen Bildlauf zerstört der <xref:System.Windows.Controls.ItemsControl>. Sie könne Konfigurationselements Wiederverwendung durch Festlegen der <xref:System.Windows.Controls.VirtualizingPanel.VirtualizationMode%2A> angefügten Eigenschaft, um <xref:System.Windows.Controls.VirtualizationMode.Recycling>.  
  
 Alle <xref:System.Windows.Controls.ItemsControl> Virtualisierung können Wiederverwenden von Containern unterstützt.  Ein Beispiel zum Aktivieren der Container-Wiederverwendung auf eine <xref:System.Windows.Controls.ListBox>, finden Sie unter [Verbesserung der Leistung Scrollen ' ListBox '](../../../../docs/framework/wpf/controls/how-to-improve-the-scrolling-performance-of-a-listbox.md).  
  
<a name="Supporting"></a>   
## <a name="supporting-bidirectional-virtualization"></a>Unterstützen der bidirektionalen Virtualisierung  
 <xref:System.Windows.Controls.VirtualizingStackPanel>bietet integrierten Unterstützung für die Virtualisierung der Benutzeroberfläche in eine Richtung, horizontal oder vertikal. Wenn Sie für Ihre Steuerelemente die bidirektionale Virtualisierung verwenden möchten, müssen Sie einen benutzerdefinierten Bereich, der erweitert implementieren die <xref:System.Windows.Controls.VirtualizingStackPanel> Klasse. Die <xref:System.Windows.Controls.VirtualizingStackPanel> Klasse macht virtuelle Methoden, wie z. B. <xref:System.Windows.Controls.VirtualizingStackPanel.OnViewportSizeChanged%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.LineUp%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.PageUp%2A>, und <xref:System.Windows.Controls.VirtualizingStackPanel.MouseWheelUp%2A>. Diese virtuellen Methoden ermöglichen es Ihnen, eine Änderung in den sichtbaren Teil einer Liste erkennen und entsprechend behandeln.  
  
<a name="Optimizing"></a>   
## <a name="optimizing-templates"></a>Optimieren von Vorlagen  
 Die visuelle Struktur enthält alle visuellen Elemente einer Anwendung.  Zusätzlich zu den direkt erstellten Objekten enthält es auch durch die Vorlagenerweiterung entstandene Objekte.  Z. B. beim Erstellen einer <xref:System.Windows.Controls.Button>, erhalten Sie zudem <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> und <xref:System.Windows.Controls.ContentPresenter> Objekte in der visuellen Struktur.  Wenn Sie Ihre Steuerelementvorlagen nicht optimiert haben, erstellen Sie so möglicherweise viele überflüssige Objekte in Ihrer visuellen Struktur.   Weitere Informationen zur visuellen Struktur finden Sie unter [Übersicht über das WPF-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
<a name="Deferred"></a>   
## <a name="deferred-scrolling"></a>Verzögertes Scrollen  
 Wenn ein Benutzer seinen Daumen über die Scrollleiste zieht, wird die Inhaltsansicht standardmäßig fortlaufend aktualisiert.  Wenn das Scrollen in Ihrem Steuerelement verlangsamt ist, ziehen Sie das verzögerte Scrollen in Betracht.  Beim verzögerten Scrollen wird der Inhalt nur aktualisiert, wenn der Benutzer seinen Daumen von der Scrollleiste nimmt.  
  
 Um verzögerte Bildlauf zu implementieren, legen Sie die <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> Eigenschaft `true`.  <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A>ist eine angefügte Eigenschaft, und legen Sie auf <xref:System.Windows.Controls.ScrollViewer> und beliebige Steuerelemente mit einer <xref:System.Windows.Controls.ScrollViewer> in der Steuerelementvorlage.  
  
<a name="Controls"></a>   
## <a name="controls-that-implement-performance-features"></a>Steuerelemente, die Leistungsfunktionen implementieren  
 In der unten stehenden Tabelle werden gängige Steuerelemente für das Anzeigen von Daten und deren Unterstützung von Leistungsfunktionen aufgelistet.  Im vorherigen Abschnitt finden Sie Informationen zum Aktivieren dieser Funktionen.  
  
|Steuerelement|Virtualisierung|Wiederverwenden von Containern|Verzögertes Scrollen|  
|-------------|--------------------|-------------------------|------------------------|  
|<xref:System.Windows.Controls.ComboBox>|Kann aktiviert werden|Kann aktiviert werden|Kann aktiviert werden|  
|<xref:System.Windows.Controls.ContextMenu>|Kann aktiviert werden|Kann aktiviert werden|Kann aktiviert werden|  
|<xref:System.Windows.Controls.DocumentViewer>|Nicht verfügbar|Nicht verfügbar|Kann aktiviert werden|  
|<xref:System.Windows.Controls.ListBox>|Standard|Kann aktiviert werden|Kann aktiviert werden|  
|<xref:System.Windows.Controls.ListView>|Standard|Kann aktiviert werden|Kann aktiviert werden|  
|<xref:System.Windows.Controls.TreeView>|Kann aktiviert werden|Kann aktiviert werden|Kann aktiviert werden|  
|<xref:System.Windows.Controls.ToolBar>|Nicht verfügbar|Nicht verfügbar|Kann aktiviert werden|  
  
> [!NOTE]
>  Ein Beispiel zum Aktivieren der Virtualisierung und Wiederverwendung auf Container für eine <xref:System.Windows.Controls.TreeView>, finden Sie unter [Verbessern der Leistung von einer ' TreeView '](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Layout](../../../../docs/framework/wpf/advanced/layout.md)  
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Steuerelemente](../../../../docs/framework/wpf/controls/index.md)  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
