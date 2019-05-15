---
title: 'Optimieren der Leistung: WPF-Steuerelementen:'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], improving performance
- container recycling [WPF]
- user interface virtualization [WPF]
ms.assetid: 45a31c43-ea8a-4546-96c8-0631b9934179
ms.openlocfilehash: 1e291e1638864176913342d02acad092f561789c
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645681"
---
# <a name="optimizing-performance-controls"></a>Optimieren der Leistung: Steuerelemente

Windows Presentation Foundation (WPF) bietet viele der allgemeine Komponenten der Benutzeroberfläche (UI), die verwendet werden, in den meisten Windows-Anwendungen. In diesem Thema werden Techniken dargestellt, mit denen Sie die Leistung Ihrer Benutzeroberfläche (UI) optimieren können.

## <a name="displaying-large-data-sets"></a>Anzeigen von großen Datasets

WPF-Steuerelemente wie z. B. die <xref:System.Windows.Controls.ListView> und <xref:System.Windows.Controls.ComboBox> werden verwendet, um eine Liste von Elementen in einer Anwendung anzeigen. Wenn die anzuzeigende Liste sehr groß ist, kann dies die Leistung der Anwendung beeinträchtigen. Dies liegt daran, dass das Standardlayoutsystem einen Layoutcontainer für jedes mit dem Listensteuerelement verknüpfte Element erstellt und dessen Layoutgröße und -position berechnet. Für gewöhnlich müssen Sie nicht alle Elemente gleichzeitig anzeigen; stattdessen zeigen Sie eine Teilmenge an, und der Benutzer scrollt durch die Liste. In diesem Fall macht es Sinn, die UI-*Virtualisierung* zu verwenden; dies bedeutet, dass die Generierung eines Elementcontainers und die damit verknüpfte Layoutberechnung verzögert werden, bis das Element sichtbar ist.

Die UI-Virtualisierung ist ein wichtiger Aspekt der Listensteuerelemente. Die UI-Virtualisierung ist nicht mit der Datenvirtualisierung zu verwechseln. Bei der UI-Virtualisierung werden nur sichtbare Elemente im Speicher gespeichert; in einem Datenbindungsszenario wird die gesamte Datenstruktur im Speicher gespeichert. Im Gegensatz dazu werden bei der Datenvisualisierung nur die Datenelemente gespeichert, die auf dem Bildschirm im Speicher sichtbar sind.

Standardmäßig ist für die UI-Virtualisierung aktiviert die <xref:System.Windows.Controls.ListView> und <xref:System.Windows.Controls.ListBox> steuert, wenn deren Listenelemente an Daten gebunden sind. <xref:System.Windows.Controls.TreeView> Virtualisierung kann aktiviert werden, durch Festlegen der <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=nameWithType> angefügte Eigenschaft zu `true`. Sollten Sie die UI-Virtualisierung für benutzerdefinierte Steuerelemente zu ermöglichen, die abgeleitet <xref:System.Windows.Controls.ItemsControl> oder vorhandene Steuerelemente, die <xref:System.Windows.Controls.StackPanel> Klasse, z. B. <xref:System.Windows.Controls.ComboBox>, können Sie festlegen, der <xref:System.Windows.Controls.ItemsControl.ItemsPanel%2A> zu <xref:System.Windows.Controls.VirtualizingStackPanel> und legen Sie <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizing%2A> zu `true`. Allerdings kann es passieren, dass Sie die UI-Virtualisierung für diese Steuerelemente deaktivieren, ohne es zu merken. Durch folgende Bedingungen kann die UI-Virtualisierung deaktiviert werden:

- Elementcontainer werden direkt hinzugefügt, die <xref:System.Windows.Controls.ItemsControl>. Angenommen, eine Anwendung explizit hinzufügt <xref:System.Windows.Controls.ListBoxItem> Objekte eine <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListBox> ist nicht virtualisiert werden. die <xref:System.Windows.Controls.ListBoxItem> Objekte.

- Elementcontainer im der <xref:System.Windows.Controls.ItemsControl> weisen unterschiedliche Datentypen. Z. B. eine <xref:System.Windows.Controls.Menu> verwendet <xref:System.Windows.Controls.Separator> Objekte können nicht implementiert Element wiederverwendet werden, da die <xref:System.Windows.Controls.Menu> enthält Objekte vom Typ <xref:System.Windows.Controls.Separator> und <xref:System.Windows.Controls.MenuItem>.

- Festlegen von <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> zu `false`.

- Festlegen von <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> zu `false`.

Bei der Virtualisierung von Elementcontainern ist es maßgeblich, zu wissen, ob Ihnen Informationen bezüglich des zusätzlichen Zustands des Elementcontainers vorliegen, der zu dem Element gehört. Falls dem so ist, müssen Sie den zusätzlichen Zustand speichern. Angenommen, Sie müssen möglicherweise ein Element innerhalb einer <xref:System.Windows.Controls.Expander> Steuerelement und die <xref:System.Windows.Controls.Expander.IsExpanded%2A> Zustand auf den Container des Elements und nicht für das Element selbst gebunden ist. Wenn der Container für ein neues Element, den aktuellen Wert der wiederverwendet wird <xref:System.Windows.Controls.Expander.IsExpanded%2A> für das neue Element verwendet wird. Zusätzlich verliert das neue Element dem richtigen <xref:System.Windows.Controls.Expander.IsExpanded%2A> Wert.

Im Moment gibt es keine WPF-Steuerelemente, die integrierte Unterstützung für die Datenvirtualisierung bieten.

## <a name="container-recycling"></a>Wiederverwenden von Containern

Eine Optimierung für die Virtualisierung der Benutzeroberfläche hinzugefügt, die in der .NET Framework 3.5 SP1 für Steuerelemente, die von erben <xref:System.Windows.Controls.ItemsControl> ist *Wiederverwenden von Containern* wodurch können auch die bildlaufleistung verbessert werden. Wenn ein <xref:System.Windows.Controls.ItemsControl> , dass die Virtualisierung der Benutzeroberfläche verwendet wird aufgefüllt wird, erstellt einen Elementcontainer für jedes Element, das einen Bildlauf durchführt, in der Ansicht und zerstört den Elementcontainer für jedes Element, das aus der Ansicht einen Bildlauf durchführt. *Wiederverwenden von Containern* aktiviert das Steuerelement, vorhandene Elementcontainer für verschiedene Datenelemente wiederzuverwenden, sodass Elementcontainer nicht fortlaufend erstellt und werden, wie die Benutzer einen Bildlauf zerstört der <xref:System.Windows.Controls.ItemsControl>. Sie können auch das Wiederverwenden von festlegen aktivieren die <xref:System.Windows.Controls.VirtualizingPanel.VirtualizationMode%2A> angefügte Eigenschaft zu <xref:System.Windows.Controls.VirtualizationMode.Recycling>.

Alle <xref:System.Windows.Controls.ItemsControl> , die Virtualisierung können Wiederverwenden von Containern unterstützt. Ein Beispiel zum Aktivieren der Wiederverwenden von Containern auf einem <xref:System.Windows.Controls.ListBox>, finden Sie unter [Verbessern der Bildlaufleistung eines Listenfelds](../controls/how-to-improve-the-scrolling-performance-of-a-listbox.md).

## <a name="supporting-bidirectional-virtualization"></a>Unterstützen der bidirektionalen Virtualisierung

<xref:System.Windows.Controls.VirtualizingStackPanel> bietet integrierten Unterstützung für die Virtualisierung der Benutzeroberfläche in einer Richtung an, entweder horizontal oder vertikal. Wenn Sie die bidirektionale Virtualisierung für Ihre Steuerelemente verwenden möchten, müssen Sie ein benutzerdefiniertes Panel, das erweitert implementieren die <xref:System.Windows.Controls.VirtualizingStackPanel> Klasse. Die <xref:System.Windows.Controls.VirtualizingStackPanel> -Klasse macht virtuelle Methoden wie z. B. <xref:System.Windows.Controls.VirtualizingStackPanel.OnViewportSizeChanged%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.LineUp%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.PageUp%2A>, und <xref:System.Windows.Controls.VirtualizingStackPanel.MouseWheelUp%2A>. Diese virtuellen Methoden können Sie eine Änderung in den sichtbaren Teil einer Liste erkennen und diese entsprechend behandeln.

## <a name="optimizing-templates"></a>Optimieren von Vorlagen

Die visuelle Struktur enthält alle visuellen Elemente einer Anwendung. Zusätzlich zu den direkt erstellten Objekten enthält es auch durch die Vorlagenerweiterung entstandene Objekte. Z. B. bei der Erstellung einer <xref:System.Windows.Controls.Button>, erhalten Sie auch <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> und <xref:System.Windows.Controls.ContentPresenter> Objekte in der visuellen Struktur. Wenn Sie Ihre Steuerelementvorlagen nicht optimiert haben, erstellen Sie so möglicherweise viele überflüssige Objekte in Ihrer visuellen Struktur. Weitere Informationen zur visuellen Struktur finden Sie unter [Übersicht über das WPF-Grafikrendering](../graphics-multimedia/wpf-graphics-rendering-overview.md).

## <a name="deferred-scrolling"></a>Verzögertes Scrollen

Wenn ein Benutzer seinen Daumen über die Scrollleiste zieht, wird die Inhaltsansicht standardmäßig fortlaufend aktualisiert. Wenn das Scrollen in Ihrem Steuerelement verlangsamt ist, ziehen Sie das verzögerte Scrollen in Betracht. Beim verzögerten Scrollen wird der Inhalt nur aktualisiert, wenn der Benutzer seinen Daumen von der Scrollleiste nimmt.

Um verzögertes Scrollen zu implementieren, legen Sie die <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> Eigenschaft `true`. <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> ist eine angefügte Eigenschaft und kann festgelegt werden, auf <xref:System.Windows.Controls.ScrollViewer> und beliebige Steuerelemente mit einem <xref:System.Windows.Controls.ScrollViewer> in seiner Steuerelementvorlage.

## <a name="controls-that-implement-performance-features"></a>Steuerelemente, die Leistungsfunktionen implementieren

In der unten stehenden Tabelle werden gängige Steuerelemente für das Anzeigen von Daten und deren Unterstützung von Leistungsfunktionen aufgelistet. Im vorherigen Abschnitt finden Sie Informationen zum Aktivieren dieser Funktionen.

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
> Ein Beispiel für das Aktivieren von Virtualisierung und wiederverwendens von Containern auf einem <xref:System.Windows.Controls.TreeView>, finden Sie unter [Verbessern der Leistung von TreeView](../controls/how-to-improve-the-performance-of-a-treeview.md).

## <a name="see-also"></a>Siehe auch

- [Layout](layout.md)
- [Layout und Entwurf](optimizing-performance-layout-and-design.md)
- [Datenbindung](optimizing-performance-data-binding.md)
- [Steuerelemente](../controls/index.md)
- [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md)
- [Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung](walkthrough-caching-application-data-in-a-wpf-application.md)
