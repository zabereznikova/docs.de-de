---
title: "Optimieren der Leistung: Steuerelemente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Wiederverwenden von Containern"
  - "Steuerelemente [WPF], Verbessern der Leistung"
  - "Virtualisierung der Benutzeroberfläche"
ms.assetid: 45a31c43-ea8a-4546-96c8-0631b9934179
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Optimieren der Leistung: Steuerelemente
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] schließt viele der allgemeinen Benutzeroberflächenkomponenten ein, die in den meisten Windows\-Anwendungen verwendet werden.  In diesem Thema werden Methoden zum Verbessern der Leistung der Benutzeroberfläche beschrieben.  
  
   
  
<a name="Displaying"></a>   
## Anzeigen von großen DataSets  
 WPF\-Steuerelemente, wie <xref:System.Windows.Controls.ListView> und <xref:System.Windows.Controls.ComboBox>, werden zum Anzeigen von Elementlisten in einer Anwendung verwendet.  Wenn die anzuzeigende Liste groß ist, kann die Leistung der Anwendung beeinträchtigt werden.  Dies ist darauf zurückzuführen, dass das Standardlayoutsystem einen Layoutcontainer für jedes Elemente erstellt, das dem Listensteuerelement zugeordnet ist, und seine Layoutgröße und Position berechnet.  In der Regel brauchen Sie nicht alle Elemente gleichzeitig anzuzeigen. Stattdessen zeigen Sie eine Teilmenge an und der Benutzer führt einen Bildlauf durch die Liste durch.  In diesem Fall ist es sinnvoll, die *Virtualisierung* der Benutzeroberfläche zu verwenden. Das heißt, die Elementcontainergenerierung und Berechnung des zugeordneten Layouts wird für ein Element zurückgestellt, bis das Element sichtbar ist.  
  
 Die Virtualisierung der Benutzeroberfläche ist ein wichtiger Aspekt von Listen\-Steuerelementen.  Die Virtualisierung der Benutzeroberfläche sollte nicht mit der Datenvirtualisierung verwechselt werden.  Bei der Virtualisierung der Benutzeroberfläche werden lediglich die sichtbaren Elemente gespeichert, in einem datengebundenen Szenario wird jedoch die gesamte Datenstruktur gespeichert.  Im Gegensatz dazu werden bei der Datenvirtualisierung nur die Datenelemente gespeichert, die auf dem Bildschirm sichtbar sind.  
  
 Standardmäßig ist die Virtualisierung der Benutzeroberfläche für die Steuerelemente <xref:System.Windows.Controls.ListView> und <xref:System.Windows.Controls.ListBox> aktiviert, wenn die Listenelemente an Daten gebunden sind.  Die <xref:System.Windows.Controls.TreeView>\-Virtualisierung kann durch Festlegen der angefügten <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=fullName>\-Eigenschaft auf `true` aktiviert werden.  Falls Sie die Virtualisierung der Benutzeroberfläche für benutzerdefinierte Steuerelemente aktivieren möchten, die von <xref:System.Windows.Controls.ItemsControl> abgeleitet sind, oder für bereits vorhandene Steuerelemente, die die <xref:System.Windows.Controls.StackPanel>\-Klasse verwenden, wie <xref:System.Windows.Controls.ComboBox>, können Sie <xref:System.Windows.Controls.ItemsControl.ItemsPanel%2A> auf <xref:System.Windows.Controls.VirtualizingStackPanel> und <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizing%2A> auf `true` festlegen.  Leider können Sie die Virtualisierung der Benutzeroberfläche für diese Steuerelemente deaktivieren, ohne sich dessen bewusst zu sein.  Im Folgenden erhalten Sie eine Liste der Bedingungen, die die Virtualisierung der Benutzeroberfläche deaktivieren.  
  
-   <xref:System.Windows.Controls.ItemsControl> werden Elementcontainer direkt hinzugefügt.  Falls z. B. eine Anwendung einem <xref:System.Windows.Controls.ListBox> ausdrücklich <xref:System.Windows.Controls.ListBoxItem>\-Objekte hinzufügt, virtualisiert <xref:System.Windows.Controls.ListBox> die <xref:System.Windows.Controls.ListBoxItem>\-Objekte nicht.  
  
-   Elementcontainer im <xref:System.Windows.Controls.ItemsControl> weisen verschiedene Typen auf.  So kann <xref:System.Windows.Controls.Menu>, das <xref:System.Windows.Controls.Separator>\-Objekte verwendet, keine Elementwiederverwendung implementieren, da <xref:System.Windows.Controls.Menu> Objekte vom Typ <xref:System.Windows.Controls.Separator> und <xref:System.Windows.Controls.MenuItem> enthält.  
  
-   <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> wurde auf `false` festgelegt.  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> wurde auf `false` festgelegt.  
  
 Ein wichtiger Aspekt, wenn Sie Elementcontainer virtualisieren, besteht darin, dass Sie zusätzliche Zustandsinformationen enthalten, die mit einem Elementcontainer zugeordnet sind, der dem Element gehört.  In diesem Fall müssen Sie den zusätzlichen Zustand speichern.  So könnte sich beispielsweise in einem <xref:System.Windows.Controls.Expander>\-Steuerelement ein Element befinden, und der Zustand <xref:System.Windows.Controls.Expander.IsExpanded%2A> ist an den Elementcontainer gebunden und nicht an das Element selbst.  Wenn der Container für ein neues Element wieder verwendet wird, wird der aktuelle Wert von <xref:System.Windows.Controls.Expander.IsExpanded%2A> für das neue Element verwendet.  Außerdem verliert das alte Element den richtigen <xref:System.Windows.Controls.Expander.IsExpanded%2A>\-Wert.  
  
 Derzeit bieten keine WPF\-Steuerelemente eine integrierte Unterstützung der Datenvirtualisierung.  
  
<a name="Container"></a>   
## Containerwiederverwendung  
 Eine Optimierung der Virtualisierung der Benutzeroberfläche, die im .NET Framework 3.5 SP1 für Steuerelemente hinzugefügt wurde, die von <xref:System.Windows.Controls.ItemsControl> erben, stellt die *Containerwiederverwendung* dar, mit der auch die Bildlaufleistung verbessert werden kann.  Wenn ein <xref:System.Windows.Controls.ItemsControl>, das die Virtualisierung der Benutzeroberfläche verwendet, mit Daten gefüllt wird, wird ein Elementcontainer für jedes Element erstellt, das durch einen Bildlauf sichtbar wird, und der Elementcontainer für jedes Element zerstört, das nicht mehr im Bildlauf sichtbar ist.  Mit der *Containerwiederverwendung* wird das Steuerelement aktiviert, um die bereits vorhandenen Elementcontainer für verschiedene Datenelemente so wieder zu verwenden, dass die Elementcontainer nicht ständig erstellt und zerstört werden, wenn der Benutzer einen Bildlauf durch <xref:System.Windows.Controls.ItemsControl> ausführt.  Sie können wählen, ob Wiederverwendung von Element zu aktivieren, indem Sie die <xref:System.Windows.Controls.VirtualizingPanel.VirtualizationMode%2A> angefügte Eigenschaft auf <xref:System.Windows.Controls.VirtualizationMode>festlegen.  
  
 Jedes <xref:System.Windows.Controls.ItemsControl>, das die Virtualisierung unterstützt, kann die Containerwiederverwendung verwenden.  Ein Beispiel zur Aktivierung der Containerwiederverwendung für ein <xref:System.Windows.Controls.ListBox> finden Sie unter [Verbessern der Bildlaufleistung eines Listenfelds](../../../../docs/framework/wpf/controls/how-to-improve-the-scrolling-performance-of-a-listbox.md).  
  
<a name="Supporting"></a>   
## Unterstützung der bidirektionalen Virtualisierung  
 <xref:System.Windows.Controls.VirtualizingStackPanel> bietet eine horizontale oder vertikale integrierte Unterstützung in eine Richtung für die Virtualisierung der Benutzeroberfläche.  Falls Sie für Ihre Steuerelemente die bidirektionale Virtualisierung verwenden möchten, müssen Sie ein benutzerdefiniertes Panel implementieren, das die <xref:System.Windows.Controls.VirtualizingStackPanel>\-Klasse erweitert.  Die <xref:System.Windows.Controls.VirtualizingStackPanel>\-Klasse macht virtuelle Methoden, wie <xref:System.Windows.Controls.VirtualizingStackPanel.OnViewportSizeChanged%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.LineUp%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.PageUp%2A> und <xref:System.Windows.Controls.VirtualizingStackPanel.MouseWheelUp%2A> verfügbar. Mit diesen virtuellen Methoden können Sie eine Veränderung im sichtbaren Teil einer Liste erkennen und entsprechend bearbeiten.  
  
<a name="Optimizing"></a>   
## Optimieren von Vorlagen  
 Die visuelle Struktur enthält alle visuellen Elemente in einer Anwendung.  Zusätzlich zu den direkt erstellten Objekten enthält es auch Objekte aufgrund der Vorlagenerweiterung.  Wenn Sie z. B. eine <xref:System.Windows.Controls.Button> erstellen, rufen Sie gleichzeitig auch <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>\- und <xref:System.Windows.Controls.ContentPresenter>\-Objekte in der visuellen Struktur ab.  Falls Sie Ihre Steuerelementvorlagen nicht optimiert haben, erstellen Sie u. U. viele zusätzliche unnötige Objekte in der visuellen Struktur.  Weitere Informationen über die visuelle Struktur finden Sie unter [Übersicht über das WPF\-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
<a name="Deferred"></a>   
## Verzögerter Bildlauf  
 Wenn der Benutzer das Bildlauffeld einer Bildlaufleiste zieht, wird die Inhaltsansicht kontinuierlich aktualisiert.  Wenn der Bildlauf im Steuerelement langsam ist, erwägen Sie die Verwendung des verzögerten Bildlaufs.  Beim verzögerten Bildlauf wird der Inhalt nur aktualisiert, wenn der Benutzer das Bildlauffeld loslässt.  
  
 Legen Sie für die Implementierung des verzögerten Bildlaufs die <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A>\-Eigenschaft auf `true` fest.  <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> ist eine angefügte Eigenschaft, die für das <xref:System.Windows.Controls.ScrollViewer>\-Objekt und jedes Steuerelement festgelegt werden kann, das in der Steuerelementvorlage ein <xref:System.Windows.Controls.ScrollViewer>\-Objekt enthält.  
  
<a name="Controls"></a>   
## Steuerelemente, die Leistungsfeatures implementieren  
 In der folgenden Tabelle sind die allgemeinen Steuerelemente zum Anzeigen von Daten und ihrer Unterstützung von Leistungsfeatures aufgeführt.  Informationen über das Aktivieren dieser Features finden Sie in den vorherigen Abschnitten.  
  
|Steuerelement|Virtualisierung|Containerwiederverwendung|Verzögerter Bildlauf|  
|-------------------|---------------------|-------------------------------|--------------------------|  
|<xref:System.Windows.Controls.ComboBox>|Kann aktiviert werden|Kann aktiviert werden|Kann aktiviert werden|  
|<xref:System.Windows.Controls.ContextMenu>|Kann aktiviert werden|Kann aktiviert werden|Kann aktiviert werden|  
|<xref:System.Windows.Controls.DocumentViewer>|Nicht verfügbar|Nicht verfügbar|Kann aktiviert werden|  
|<xref:System.Windows.Controls.ListBox>|Standardwert|Kann aktiviert werden|Kann aktiviert werden|  
|<xref:System.Windows.Controls.ListView>|Standardwert|Kann aktiviert werden|Kann aktiviert werden|  
|<xref:System.Windows.Controls.TreeView>|Kann aktiviert werden|Kann aktiviert werden|Kann aktiviert werden|  
|<xref:System.Windows.Controls.ToolBar>|Nicht verfügbar|Nicht verfügbar|Kann aktiviert werden|  
  
> [!NOTE]
>  Ein Beispiel über das Aktivieren von Virtualisierung und Containerwiederverwendung in einer <xref:System.Windows.Controls.TreeView> finden Sie unter [Verbessern der Leistung von TreeView](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md).  
  
## Siehe auch  
 [Layout](../../../../docs/framework/wpf/advanced/layout.md)   
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Steuerelemente](../../../../docs/framework/wpf/controls/index.md)   
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF\-Anwendung](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)