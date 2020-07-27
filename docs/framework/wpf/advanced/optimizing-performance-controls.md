---
title: Optimieren der Steuerungs Leistung
description: Windows Presentation Foundation umfasst viele allgemeine Komponenten, die in den meisten Windows-Anwendungen verwendet werden. Erfahren Sie, wie Sie die Leistung der Benutzeroberfläche steigern.
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], improving performance
- container recycling [WPF]
- user interface virtualization [WPF]
ms.assetid: 45a31c43-ea8a-4546-96c8-0631b9934179
ms.openlocfilehash: de348dd93e5710b5b81af035ec7aa56e01dc4981
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168299"
---
# <a name="optimizing-performance-controls"></a>Optimieren der Leistung: Steuerelemente

Windows Presentation Foundation (WPF) umfasst viele der allgemeinen Benutzeroberflächen Komponenten, die in den meisten Windows-Anwendungen verwendet werden. In diesem Thema werden Techniken dargestellt, mit denen Sie die Leistung Ihrer Benutzeroberfläche (UI) optimieren können.

## <a name="displaying-large-data-sets"></a>Anzeigen von großen Datasets

WPF-Steuerelemente, wie z <xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.ComboBox> . b. und, werden verwendet, um Listen von Elementen in einer Anwendung anzuzeigen. Wenn die anzuzeigende Liste sehr groß ist, kann dies die Leistung der Anwendung beeinträchtigen. Dies liegt daran, dass das Standardlayoutsystem einen Layoutcontainer für jedes mit dem Listensteuerelement verknüpfte Element erstellt und dessen Layoutgröße und -position berechnet. Für gewöhnlich müssen Sie nicht alle Elemente gleichzeitig anzeigen; stattdessen zeigen Sie eine Teilmenge an, und der Benutzer scrollt durch die Liste. In diesem Fall macht es Sinn, die UI-*Virtualisierung* zu verwenden; dies bedeutet, dass die Generierung eines Elementcontainers und die damit verknüpfte Layoutberechnung verzögert werden, bis das Element sichtbar ist.

Die UI-Virtualisierung ist ein wichtiger Aspekt der Listensteuerelemente. Die UI-Virtualisierung ist nicht mit der Datenvirtualisierung zu verwechseln. Bei der UI-Virtualisierung werden nur sichtbare Elemente im Speicher gespeichert; in einem Datenbindungsszenario wird die gesamte Datenstruktur im Speicher gespeichert. Im Gegensatz dazu werden bei der Datenvisualisierung nur die Datenelemente gespeichert, die auf dem Bildschirm im Speicher sichtbar sind.

Standardmäßig ist die UI-Virtualisierung für das-Steuerelement und das-Steuerelement aktiviert, <xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.ListBox> Wenn die Listenelemente an Daten gebunden sind. <xref:System.Windows.Controls.TreeView>die Virtualisierung kann aktiviert werden, indem die <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=nameWithType> angefügte-Eigenschaft auf festgelegt wird `true` . Wenn Sie die UI-Virtualisierung für benutzerdefinierte Steuerelemente aktivieren möchten, die von <xref:System.Windows.Controls.ItemsControl> oder vorhandenen Element Steuerelementen abgeleitet werden, die die- <xref:System.Windows.Controls.StackPanel> Klasse verwenden, wie z <xref:System.Windows.Controls.ComboBox> . b., können Sie <xref:System.Windows.Controls.ItemsControl.ItemsPanel%2A> auf festlegen <xref:System.Windows.Controls.VirtualizingStackPanel> und <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizing%2A> auf festlegen `true` . Allerdings kann es passieren, dass Sie die UI-Virtualisierung für diese Steuerelemente deaktivieren, ohne es zu merken. Durch folgende Bedingungen kann die UI-Virtualisierung deaktiviert werden:

- Element Container werden direkt hinzugefügt <xref:System.Windows.Controls.ItemsControl> . Wenn eine Anwendung z. b. explizit <xref:System.Windows.Controls.ListBoxItem> einem Objekte hinzufügt <xref:System.Windows.Controls.ListBox> , werden <xref:System.Windows.Controls.ListBox> die Objekte von nicht virtualisiert <xref:System.Windows.Controls.ListBoxItem> .

- Element Container in <xref:System.Windows.Controls.ItemsControl> sind von unterschiedlichen Typen. Beispielsweise kann ein <xref:System.Windows.Controls.Menu> -Objekt, das-Objekte verwendet, die Wiederverwendung <xref:System.Windows.Controls.Separator> von Elementen nicht implementieren, da die <xref:System.Windows.Controls.Menu> Objekte vom Typ <xref:System.Windows.Controls.Separator> und enthält <xref:System.Windows.Controls.MenuItem>

- Legen <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> Sie auf fest `false` .

- Legen <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> Sie auf fest `false` .

Bei der Virtualisierung von Elementcontainern ist es maßgeblich, zu wissen, ob Ihnen Informationen bezüglich des zusätzlichen Zustands des Elementcontainers vorliegen, der zu dem Element gehört. Falls dem so ist, müssen Sie den zusätzlichen Zustand speichern. Angenommen, Sie verfügen über ein Element, das in einem <xref:System.Windows.Controls.Expander> -Steuerelement enthalten <xref:System.Windows.Controls.Expander.IsExpanded%2A> ist, und der-Zustand ist an den Container des Elements und nicht an das Element selbst gebunden. Wenn der Container für ein neues Element wieder verwendet wird, wird der aktuelle Wert von <xref:System.Windows.Controls.Expander.IsExpanded%2A> für das neue Element verwendet. Außerdem verliert das alte Element den richtigen <xref:System.Windows.Controls.Expander.IsExpanded%2A> Wert.

Im Moment gibt es keine WPF-Steuerelemente, die integrierte Unterstützung für die Datenvirtualisierung bieten.

## <a name="container-recycling"></a>Wiederverwenden von Containern

Eine Optimierung der benutzeroberflächenvirtualisierung, die in der .NET Framework 3,5 SP1 für Steuerelemente, die von erben, hinzugefügt <xref:System.Windows.Controls.ItemsControl> wird, ist die Wiederverwendung von *Containern,* wodurch auch die Leistung Wenn ein-Objekt <xref:System.Windows.Controls.ItemsControl> , das die UI-Virtualisierung verwendet, aufgefüllt wird, erstellt es einen Element Container für jedes Element, das in die Ansicht verwandelt und den Element Container für jedes Element zerstört, das aus der Ansicht herausrollt. Durch die Wiederverwendung von *Containern* kann das Steuerelement die vorhandenen Element Container für verschiedene Datenelemente wieder verwenden, sodass Element Container nicht ständig erstellt und zerstört werden, wenn der Benutzer einen Bildlauf durchführt <xref:System.Windows.Controls.ItemsControl> . Sie können die Wiederverwendung von Elementen aktivieren, indem Sie die <xref:System.Windows.Controls.VirtualizingPanel.VirtualizationMode%2A> angefügte-Eigenschaft auf festlegen <xref:System.Windows.Controls.VirtualizationMode.Recycling> .

Alle <xref:System.Windows.Controls.ItemsControl> , die Virtualisierung unterstützen, können die Container Wiederverwendung verwenden. Ein Beispiel für das Aktivieren der Wiederverwendung von Containern in einem finden Sie unter <xref:System.Windows.Controls.ListBox> [verbessern der Bild Laufleistung eines ListBox](../controls/how-to-improve-the-scrolling-performance-of-a-listbox.md)-Steuer Felds.

## <a name="supporting-bidirectional-virtualization"></a>Unterstützung bidirektionaler Virtualisierung

<xref:System.Windows.Controls.VirtualizingStackPanel>bietet integrierte Unterstützung für die UI-Virtualisierung in einer Richtung, entweder horizontal oder vertikal. Wenn Sie die bidirektionale Virtualisierung für Ihre Steuerelemente verwenden möchten, müssen Sie ein benutzerdefiniertes Panel implementieren, das die- <xref:System.Windows.Controls.VirtualizingStackPanel> Klasse erweitert. Die- <xref:System.Windows.Controls.VirtualizingStackPanel> Klasse macht virtuelle Methoden verfügbar <xref:System.Windows.Controls.VirtualizingStackPanel.OnViewportSizeChanged%2A> , z. b <xref:System.Windows.Controls.VirtualizingStackPanel.LineUp%2A> .,, <xref:System.Windows.Controls.VirtualizingStackPanel.PageUp%2A> und <xref:System.Windows.Controls.VirtualizingStackPanel.MouseWheelUp%2A> . Mit diesen virtuellen Methoden können Sie eine Änderung im sichtbaren Teil einer Liste erkennen und entsprechend behandeln.

## <a name="optimizing-templates"></a>Optimieren von Vorlagen

Die visuelle Struktur enthält alle visuellen Elemente einer Anwendung. Zusätzlich zu den direkt erstellten Objekten enthält es auch durch die Vorlagenerweiterung entstandene Objekte. Wenn Sie z. b. ein erstellen <xref:System.Windows.Controls.Button> , erhalten Sie auch <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> -und- <xref:System.Windows.Controls.ContentPresenter> Objekte in der visuellen Struktur. Wenn Sie Ihre Steuerelementvorlagen nicht optimiert haben, erstellen Sie so möglicherweise viele überflüssige Objekte in Ihrer visuellen Struktur. Weitere Informationen zur visuellen Struktur finden Sie unter [Übersicht über das WPF-Grafikrendering](../graphics-multimedia/wpf-graphics-rendering-overview.md).

## <a name="deferred-scrolling"></a>Verzögertes Scrollen

Wenn ein Benutzer seinen Daumen über die Scrollleiste zieht, wird die Inhaltsansicht standardmäßig fortlaufend aktualisiert. Wenn das Scrollen in Ihrem Steuerelement verlangsamt ist, ziehen Sie das verzögerte Scrollen in Betracht. Beim verzögerten Scrollen wird der Inhalt nur aktualisiert, wenn der Benutzer seinen Daumen von der Scrollleiste nimmt.

Legen Sie die-Eigenschaft auf fest, um das verzögerte scrollen zu implementieren <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> `true` . <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A>ist eine angefügte Eigenschaft, die auf festgelegt werden kann <xref:System.Windows.Controls.ScrollViewer> , und ein beliebiges Steuerelement, das über eine <xref:System.Windows.Controls.ScrollViewer> in der Steuerelement Vorlage

## <a name="controls-that-implement-performance-features"></a>Steuerelemente, die Leistungs Features implementieren

In der unten stehenden Tabelle werden gängige Steuerelemente für das Anzeigen von Daten und deren Unterstützung von Leistungsfunktionen aufgelistet. Im vorherigen Abschnitt finden Sie Informationen zum Aktivieren dieser Funktionen.

|Control|Virtualisierung|Wiederverwenden von Containern|Verzögertes Scrollen|
|-------------|--------------------|-------------------------|------------------------|
|<xref:System.Windows.Controls.ComboBox>|Kann aktiviert werden|Kann aktiviert werden|Kann aktiviert werden|
|<xref:System.Windows.Controls.ContextMenu>|Kann aktiviert werden|Kann aktiviert werden|Kann aktiviert werden|
|<xref:System.Windows.Controls.DocumentViewer>|Nicht verfügbar|Nicht verfügbar|Kann aktiviert werden|
|<xref:System.Windows.Controls.ListBox>|Standard|Kann aktiviert werden|Kann aktiviert werden|
|<xref:System.Windows.Controls.ListView>|Standard|Kann aktiviert werden|Kann aktiviert werden|
|<xref:System.Windows.Controls.TreeView>|Kann aktiviert werden|Kann aktiviert werden|Kann aktiviert werden|
|<xref:System.Windows.Controls.ToolBar>|Nicht verfügbar|Nicht verfügbar|Kann aktiviert werden|

> [!NOTE]
> Ein Beispiel zum Aktivieren der Virtualisierung und Wiederverwendung von Containern in einem <xref:System.Windows.Controls.TreeView> finden Sie unter [verbessern der Leistung von TreeView](../controls/how-to-improve-the-performance-of-a-treeview.md).

## <a name="see-also"></a>Weitere Informationen

- [Layout](layout.md)
- [Layout und Entwurf](optimizing-performance-layout-and-design.md)
- [Datenbindung](optimizing-performance-data-binding.md)
- [Steuerelemente](../controls/index.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung](walkthrough-caching-application-data-in-a-wpf-application.md)
