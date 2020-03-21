---
title: Übersicht über Panel-Elemente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF], about Panel control
- controls [WPF], Panel
ms.assetid: f73644af-9941-4611-8754-6d4cef03fc44
ms.openlocfilehash: 7810bfbf4f5bedf51e0797a4b9017f589e0b0a8a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187578"
---
# <a name="panels-overview"></a>Übersicht über Panel-Elemente
<xref:System.Windows.Controls.Panel>Elemente sind Komponenten, die das Rendern von Elementen steuern – ihre Größe und Abmessungen, ihre Position und die Anordnung ihres untergeordneten Inhalts. Der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet eine Reihe <xref:System.Windows.Controls.Panel> vordefinierter Elemente sowie <xref:System.Windows.Controls.Panel> die Möglichkeit, benutzerdefinierte Elemente zu erstellen.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
- [Die Panel-Klasse](#Panels_view_from_10000_feet)  
  
- [Allgemeine Member von Panel-Elementen](#Panels_declared_members)  
  
- [Abgeleitete Panel-Elemente](#Panels_derived_elements)  
  
- [Panels der Benutzeroberfläche](#Panels_main_UI_elements)  
  
- [Geschachtelte Panel-Elemente](#Panels_nested_panel_elements)  
  
- [Benutzerdefinierte Panel-Elemente](#Panels_custom_panel_elements)  
  
- [Unterstützung der Lokalisierung/Globalisierung](#Panels_global_localization)  
  
<a name="Panels_view_from_10000_feet"></a>
## <a name="the-panel-class"></a>Die Panel-Klasse  
 <xref:System.Windows.Controls.Panel>ist die Basisklasse für alle Elemente, die Layoutunterstützung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]bereitstellen. Abgeleitete <xref:System.Windows.Controls.Panel> Elemente werden verwendet, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] um Elemente in und Code zu positionieren und anzuordnen.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält eine umfassende Auflistung abgeleiteter Panelimplementierungen, die komplexe Layouts zulassen. Diese abgeleiteten Klassen machen Eigenschaften und Methoden verfügbar, die die meisten [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Standardszenarios zulassen. Entwickler, die kein untergeordnetes Arrangementverhalten finden können, das ihren Anforderungen <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> <xref:System.Windows.FrameworkElement.MeasureOverride%2A> entspricht, können neue Layouts erstellen, indem sie die und die Methoden überschreiben. Weitere Informationen über das Verhalten benutzerdefinierter Layouts finden Sie unter [Benutzerdefinierte Panel-Elemente](#Panels_custom_panel_elements).  
  
<a name="Panels_declared_members"></a>
## <a name="panel-common-members"></a>Allgemeine Panel-Elemente  
 Alle <xref:System.Windows.Controls.Panel> Elemente unterstützen die Basisgrößen- <xref:System.Windows.FrameworkElement>und <xref:System.Windows.FrameworkElement.Height%2A>Positionierungseigenschaften, die durch definiert sind, einschließlich , <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, , <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, und <xref:System.Windows.FrameworkElement.LayoutTransform%2A>. Weitere Informationen zu Positionierungseigenschaften, die durch <xref:System.Windows.FrameworkElement>definiert sind, finden Sie unter [Ausrichtung, Ränder und Auffüllungsübersicht](../advanced/alignment-margins-and-padding-overview.md).  
  
 <xref:System.Windows.Controls.Panel>macht zusätzliche Eigenschaften verfügbar, die für das Verständnis und die Verwendung des Layouts von entscheidender Bedeutung sind. Die <xref:System.Windows.Controls.Panel.Background%2A> Eigenschaft wird verwendet, um den Bereich zwischen den <xref:System.Windows.Media.Brush>Grenzen eines abgeleiteten Bedienfeldelements mit einem zu füllen. <xref:System.Windows.Controls.Panel.Children%2A>stellt die untergeordnete Auflistung <xref:System.Windows.Controls.Panel> von Elementen dar, aus denen der besteht. <xref:System.Windows.Controls.Panel.InternalChildren%2A>stellt den Inhalt <xref:System.Windows.Controls.Panel.Children%2A> der Auflistung und die durch die Datenbindung generierten Elemente dar. Beide bestehen <xref:System.Windows.Controls.UIElementCollection> aus einem von untergeordneten Elementen, die im übergeordneten <xref:System.Windows.Controls.Panel>Element gehostet werden.  
  
 Panel macht auch <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> eine angefügte Eigenschaft verfügbar, die verwendet <xref:System.Windows.Controls.Panel>werden kann, um eine mehrschichtige Reihenfolge in einer abgeleiteten zu erreichen. Mitglieder einer <xref:System.Windows.Controls.Panel.Children%2A> Panelsammlung mit einem <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> höheren Wert werden vor <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> Personen mit einem niedrigeren Wert angezeigt. Dies ist besonders nützlich <xref:System.Windows.Controls.Canvas> <xref:System.Windows.Controls.Grid> für Panels, wie und die es Kindern ermöglichen, denselben Koordinatenraum gemeinsam zu nutzen.  
  
 <xref:System.Windows.Controls.Panel>definiert auch <xref:System.Windows.Controls.Panel.OnRender%2A> die Methode, die verwendet werden kann, um <xref:System.Windows.Controls.Panel>das Standarddarstellungsverhalten einer zu überschreiben.  
  
#### <a name="attached-properties"></a>Angefügte Eigenschaften  
 Abgeleitete Panel-Elemente machen umfassenden Gebrauch von angefügten Eigenschaften. Eine attached-Eigenschaft ist eine spezialisierte Form der Abhängigkeitseigenschaft, die nicht über die herkömmliche Common Language Runtime (CLR)-Eigenschaft "wrapper" verfügt. Angefügte Eigenschaften haben eine besondere Syntax in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], die in einigen der folgenden Beispiele dargestellt sind.  
  
 Ein Zweck einer angefügten Eigenschaft ist es, untergeordnete Elemente zum Speichern eindeutiger Werte einer Eigenschaft zuzulassen, die eigentlich durch ein übergeordnetes Element definiert ist. Diese Anwendung dieser Funktion besitzt untergeordnete Elemente, die das übergeordnete Element darüber informieren, wie sie in [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dargestellt werden wollen, was sehr nützlich für das Anwendungslayout ist. Weitere Informationen finden Sie unter [Übersicht über angefügte Eigenschaften](../advanced/attached-properties-overview.md).  
  
<a name="Panels_derived_elements"></a>
## <a name="derived-panel-elements"></a>Abgeleitete Panel-Elemente  
 Viele Objekte leiten <xref:System.Windows.Controls.Panel>sich von ab, aber nicht alle sind für die Verwendung als Root-Layoutanbieter vorgesehen. Es gibt sechs definierte<xref:System.Windows.Controls.Canvas> <xref:System.Windows.Controls.DockPanel>Panelklassen <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.VirtualizingStackPanel>( <xref:System.Windows.Controls.WrapPanel>, , <xref:System.Windows.Controls.Grid>, , [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]und ), die speziell für das Erstellen von Anwendung entwickelt wurden.  
  
 Jedes Panel-Element kapselt seine eigene besondere Funktionalität, wie in der folgenden Tabelle dargestellt.  
  
|Elementname|Benutzeroberflächen-Panel?|Beschreibung|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Ja|Definiert einen Bereich, innerhalb dem Sie untergeordnete Elemente <xref:System.Windows.Controls.Canvas> explizit nach Koordinaten relativ zum Bereich positionieren können.|  
|<xref:System.Windows.Controls.DockPanel>|Ja|Definiert einen Bereich, in dem Sie untergeordnete Elemente entweder horizontal oder vertikal relativ zueinander anordnen können.|  
|<xref:System.Windows.Controls.Grid>|Ja|Definiert einen flexiblen Rasterbereich mit Spalten und Zeilen. Untergeordnete Elemente <xref:System.Windows.Controls.Grid> eines können mit <xref:System.Windows.FrameworkElement.Margin%2A> der Eigenschaft präzise positioniert werden.|  
|<xref:System.Windows.Controls.StackPanel>|Ja|Ordnet untergeordnete Elemente in einer einzelnen Zeile an, die horizontal oder vertikal ausgerichtet werden kann.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|Nein |Behandelt das Layout von Registerkartenschaltflächen in einer <xref:System.Windows.Controls.TabControl>.|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|Nein |Ordnet Inhalte innerhalb <xref:System.Windows.Controls.ToolBar> eines Steuerelements an.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|Nein |<xref:System.Windows.Controls.Primitives.UniformGrid>wird verwendet, um Untergeordnete Elemente in einem Raster mit allen gleichen Zellengrößen anzuordnen.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|Nein |Stellt eine Basisklasse für Panels bereit, die ihre untergeordnete Auflistung „virtualisieren“ kann.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|Ja|Ordnet Inhalt an und virtualisiert ihn in einer einzelnen Zeile, die horizontal oder vertikal ausgerichtet werden kann.|  
|<xref:System.Windows.Controls.WrapPanel>|Ja|<xref:System.Windows.Controls.WrapPanel>positioniert untergeordnete Elemente in sequenzieller Position von links nach rechts und bricht den Inhalt in die nächste Zeile am Rand des enthaltenden Felds. Die nachfolgende Sortierung erfolgt sequenziell von oben nach <xref:System.Windows.Controls.WrapPanel.Orientation%2A> unten oder von rechts nach links, abhängig vom Wert der Eigenschaft.|  
  
<a name="Panels_main_UI_elements"></a>
## <a name="user-interface-panels"></a>Panels der Benutzeroberfläche  
 Es stehen sechs Panelklassen zur [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Verfügung, die <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Grid>für <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.VirtualizingStackPanel>die <xref:System.Windows.Controls.WrapPanel>Unterstützung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von Szenarien optimiert sind: <xref:System.Windows.Controls.Canvas>, , , , , und . Diese Panel-Elemente sind einfach zu verwenden und vielseitig und erweiterbar genug für die meisten Anwendungen.  
  
 Jedes <xref:System.Windows.Controls.Panel> abgeleitete Element behandelt Größenbeschränkungen unterschiedlich. Wenn Sie <xref:System.Windows.Controls.Panel> verstehen, wie ein Handle Abhängigkeiten in horizontaler oder vertikaler Richtung behandelt, kann das Layout besser vorhersagbar sein.  
  
|**Panelname**|**X-Dimension**|**Y-Dimension**|  
|--------------------|----------------------|----------------------|  
|<xref:System.Windows.Controls.Canvas>|Eingeschränkt auf Inhalt|Eingeschränkt auf Inhalt|  
|<xref:System.Windows.Controls.DockPanel>|Beschränkt|Beschränkt|  
|<xref:System.Windows.Controls.StackPanel>(Vertikale Ausrichtung)|Beschränkt|Eingeschränkt auf Inhalt|  
|<xref:System.Windows.Controls.StackPanel>(Horizontale Ausrichtung)|Eingeschränkt auf Inhalt|Beschränkt|  
|<xref:System.Windows.Controls.Grid>|Beschränkt|Eingeschränkt, außer in <xref:System.Windows.GridUnitType.Auto> Fällen, in denen für Zeilen und Spalten gelten|  
|<xref:System.Windows.Controls.WrapPanel>|Eingeschränkt auf Inhalt|Eingeschränkt auf Inhalt|  
  
 Eine ausführlichere Beschreibung und Verwendungsbeispiele für jedes dieser Elemente finden Sie weiter unten.  
  
<a name="Panels_overview_Canvas_subsection"></a>
### <a name="canvas"></a>Canvas  
 Das <xref:System.Windows.Controls.Canvas> Element ermöglicht die Positionierung des Inhalts nach absoluten *x-* und *y-Koordinaten.* Elemente können in einer eindeutigen Position gezeichnet werden; alternativ bestimmt die Reihenfolge, in der Sie im Markup erscheinen, die Reihenfolge, in der die Elemente gezeichnet werden, wenn Elemente die gleichen Koordinaten verwenden.  
  
 <xref:System.Windows.Controls.Canvas>bietet die flexibelste Layoutunterstützung aller <xref:System.Windows.Controls.Panel>. Höhen- und Breiteneigenschaften werden verwendet, um den Bereich des Zeichenbereichs zu definieren, <xref:System.Windows.Controls.Canvas>und Elementen innerhalb werden absolute Koordinaten relativ zum Bereich des übergeordneten Objekts zugewiesen. Vier angefügte <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>Eigenschaften <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=nameWithType>, und , ermöglichen eine <xref:System.Windows.Controls.Canvas>feine Steuerung der Objektplatzierung innerhalb eines , sodass der Entwickler Elemente genau auf dem Bildschirm positionieren und anordnen kann.  
  
#### <a name="cliptobounds-within-a-canvas"></a>ClipToBounds innerhalb eines Canvas  
 <xref:System.Windows.Controls.Canvas>können untergeordnete Elemente an jeder beliebigen Position auf dem Bildschirm positionieren, auch an Koordinaten, die außerhalb der eigenen definierten <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A>sind. Darüber <xref:System.Windows.Controls.Canvas> hinaus ist nicht von der Größe seiner Kinder betroffen. Daher ist es möglich, dass ein untergeordnetes Element andere Elemente außerhalb <xref:System.Windows.Controls.Canvas>des umgrenzenden Rechtecks des übergeordneten Elements überzeichnet. Das Standardverhalten <xref:System.Windows.Controls.Canvas> von a besteht darin, dass untergeordnete Elemente <xref:System.Windows.Controls.Canvas>außerhalb der Grenzen des übergeordneten Elements gezeichnet werden können. Wenn dieses Verhalten unerwünscht <xref:System.Windows.UIElement.ClipToBounds%2A> ist, kann `true`die Eigenschaft auf festgelegt werden. Dies <xref:System.Windows.Controls.Canvas> bewirkt, dass auf seine eigene Größe abgeschnitten wird. <xref:System.Windows.Controls.Canvas>ist das einzige Layoutelement, mit dem untergeordnete Elemente außerhalb ihrer Grenzen gezeichnet werden können.  
  
 Diese Verhalten wird grafisch im [Width Properties Comparison Sample (Beispiel des Vergleich der Width-Eigenschaften)](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties) dargestellt.  
  
#### <a name="defining-and-using-a-canvas"></a>Definieren und Verwenden eines Canvas  
 A <xref:System.Windows.Controls.Canvas> kann einfach durch Verwendung [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oder Code instanziiert werden. Im folgenden Beispiel wird <xref:System.Windows.Controls.Canvas> veranschaulicht, wie Sie Inhalte zum absoluten Positionieren verwenden. Dieser Code erzeugt drei 100-Pixel-Quadrate. Das erste Quadrat ist rot, und die obere linke Position (*x, y*) ist als (0, 0) festgelegt. Das zweite Quadrat ist grün, und die obere linke Position ist (100, 100), direkt unterhalb und rechts vom ersten Quadrat. Das dritte Quadrat ist blau, und die obere linke Position ist (50, 50), daher umfasst es den unteren rechten Quadranten des ersten Quadrats und den oberen linken Quadranten des zweiten. Da das dritte Quadrat zuletzt angeordnet wird, erscheint es als obenliegend – das bedeutet, dass die überlappenden Teile die Farbe des dritten Quadrats annehmen.  
  
 [!code-csharp[CanvasOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Ein typisches Canvas-Element.](./media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>
### <a name="dockpanel"></a>DockPanel  
 Das <xref:System.Windows.Controls.DockPanel> Element <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> verwendet die angefügte Eigenschaft als in untergeordneten Inhaltselementen festgelegt, um Inhalt entlang der Ränder eines Containers zu positionieren. Wenn <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> auf <xref:System.Windows.Controls.Dock.Top> oder <xref:System.Windows.Controls.Dock.Bottom>gesetzt, werden untergeordnete Elemente über oder untereinander positioniert. Wenn <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> auf <xref:System.Windows.Controls.Dock.Left> oder <xref:System.Windows.Controls.Dock.Right>gesetzt, werden untergeordnete Elemente links oder rechts voneinander positioniert. Die <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> Eigenschaft bestimmt die Position des endgültigen Elements, das als untergeordnetes Element einer <xref:System.Windows.Controls.DockPanel>hinzugefügt wird.  
  
 Sie können <xref:System.Windows.Controls.DockPanel> eine Gruppe verwandter Steuerelemente positionieren, z. B. eine Reihe von Schaltflächen. Alternativ können Sie damit ein "Paned" [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]erstellen, ähnlich dem in Microsoft Outlook.  
  
#### <a name="sizing-to-content"></a>Anpassen der Größe an Inhalt  
 Wenn <xref:System.Windows.FrameworkElement.Height%2A> seine <xref:System.Windows.FrameworkElement.Width%2A> und Eigenschaften <xref:System.Windows.Controls.DockPanel> nicht angegeben sind, größen auf seinen Inhalt. Die Größe kann sich erhöhen oder verringern, um die Größe der untergeordneten Elemente aufnehmen zu können. Wenn diese Eigenschaften jedoch angegeben werden und kein Platz mehr <xref:System.Windows.Controls.DockPanel> für das nächste angegebene untergeordnete Element vorhanden ist, wird dieses untergeordnete Element oder nachfolgende untergeordnete Elemente nicht angezeigt und nachfolgende untergeordnete Elemente nicht gemessen.  
  
#### <a name="lastchildfill"></a>LastChildFill  
 Standardmäßig "füllt" das <xref:System.Windows.Controls.DockPanel> letzte untergeordnete Element eines Elements den verbleibenden, nicht zugewiesenen Speicherplatz. Wenn dieses Verhalten nicht gewünscht <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> ist, legen Sie die Eigenschaft auf fest. `false`  
  
#### <a name="defining-and-using-a-dockpanel"></a>Definieren und Verwenden von DockPanel  
 Im folgenden Beispiel wird veranschaulicht, <xref:System.Windows.Controls.DockPanel>wie Speicherplatz mithilfe einer partitioniert wird. Fünf <xref:System.Windows.Controls.Border> Elemente werden als untergeordnete <xref:System.Windows.Controls.DockPanel>Elemente eines Elternteils hinzugefügt. Jeder verwendet eine andere <xref:System.Windows.Controls.DockPanel> Positionierungseigenschaft von a, um Speicherplatz zu partitionieren. Das letzte Element „füllt“ den verbleibenden, nicht zugeordneten Platz.  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Ein typisches DockPanel-Szenario.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>
### <a name="grid"></a>Raster  
 Das <xref:System.Windows.Controls.Grid> Element führt die Funktionalität eines absoluten Positionierungs- und Tabellarischen Datensteuerelements zusammen. A <xref:System.Windows.Controls.Grid> ermöglicht es Ihnen, Elemente einfach zu positionieren und zu stilen. <xref:System.Windows.Controls.Grid>ermöglicht es Ihnen, flexible Zeilen- und Spaltengruppierungen zu definieren, und <xref:System.Windows.Controls.Grid> bietet sogar einen Mechanismus, um Größeninformationen zwischen mehreren Elementen gemeinsam zu nutzen.  
  
#### <a name="how-is-grid-different-from-table"></a>Wie unterscheidet sich Grid von Table?  
 <xref:System.Windows.Documents.Table>und <xref:System.Windows.Controls.Grid> teilen Sie einige gemeinsame Funktionen, aber jede ist am besten für verschiedene Szenarien geeignet. A <xref:System.Windows.Documents.Table> ist für die Verwendung innerhalb von Flow-Inhalten konzipiert (weitere Informationen zum Flow-Inhalt finden Sie unter [Flussdokumentübersicht).](../advanced/flow-document-overview.md) Raster eignen sich am Besten für die Verwendung in Formularen (im Grunde außerhalb von fortlaufendem Inhalt). Innerhalb <xref:System.Windows.Documents.FlowDocument>von <xref:System.Windows.Documents.Table> unterstützt Flow Content-Verhalten wie Paginierung, Spaltenreflow <xref:System.Windows.Controls.Grid> und Inhaltsauswahl, während a nicht. A <xref:System.Windows.Controls.Grid> hingegen wird am besten außerhalb eines <xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.Controls.Grid> aus vielen Gründen verwendet, einschließlich <xref:System.Windows.Documents.Table> der Hinzusagung von Elementen, die auf einem Zeilen- und Spaltenindex basieren, nicht. Das <xref:System.Windows.Controls.Grid> Element ermöglicht die Schichtung von untergeordneten Inhalten, sodass mehr als ein Element innerhalb einer einzelnen "Zelle" vorhanden ist. <xref:System.Windows.Documents.Table>unterstützt keine Layering. Untergeordnete Elemente <xref:System.Windows.Controls.Grid> eines können absolut relativ zum Bereich ihrer "Zell"-Grenzen positioniert werden. <xref:System.Windows.Documents.Table>unterstützt diese Funktion nicht. Schließlich ist <xref:System.Windows.Controls.Grid> ein leichteres <xref:System.Windows.Documents.Table>Gewicht als ein .  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>Größenanpassungsverhalten von Spalten und Zeilen  
 Spalten und Zeilen, <xref:System.Windows.Controls.Grid> die innerhalb <xref:System.Windows.GridUnitType.Star> einer definiert sind, können die Größe nutzen, um den verbleibenden Speicherplatz proportional zu verteilen. Wenn <xref:System.Windows.GridUnitType.Star> diese Spalte oder Zeile als Höhe oder Breite einer Zeile oder Spalte ausgewählt ist, erhält sie einen gewichteten Anteil des verbleibenden verfügbaren Speicherplatzes. Dies steht <xref:System.Windows.GridUnitType.Auto>im Gegensatz zu , die den Speicherplatz gleichmäßig basierend auf der Größe des Inhalts innerhalb einer Spalte oder Zeile verteilt. Dieser Wert wird als `*` oder `2*` ausgedrückt, wenn [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] verwendet wird. Im ersten Fall würde die Zeile oder Spalte den verfügbaren Platz einmal erhalten, im zweiten Fall zweimal, usw. Durch die Kombination dieser Technik, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> um <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> den `Stretch` Raum proportional mit einem und dem Wert davon zu verteilen, ist es möglich, den Layoutraum nach Prozent des Bildschirmraums zu partitionieren. <xref:System.Windows.Controls.Grid>ist das einzige Layout-Panel, das Speicherplatz auf diese Weise verteilen kann.  
  
#### <a name="defining-and-using-a-grid"></a>Definieren und Verwenden eines Rasters  
 Im folgenden Beispiel wird [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] veranschaulicht, wie Sie ein ähnliches erstellen, wie es im Dialogfeld Ausführen im Windows-Startmenü zu finden ist.  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Ein typisches Rasterelement.](./media/avalon-run-dialog.PNG "avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>
### <a name="stackpanel"></a>StackPanel  
 Mit <xref:System.Windows.Controls.StackPanel> A können Sie Elemente in eine zugewiesene Richtung "stapeln". Die Standardrichtung eines Stapels ist vertikal. Die <xref:System.Windows.Controls.StackPanel.Orientation%2A> Eigenschaft kann verwendet werden, um den Inhaltsfluss zu steuern.  
  
#### <a name="stackpanel-vs-dockpanel"></a>StackPanel vs. DockPanel  
 Obwohl <xref:System.Windows.Controls.DockPanel> auch untergeordnete Elemente "stapeln" können <xref:System.Windows.Controls.DockPanel> und <xref:System.Windows.Controls.StackPanel> in einigen Verwendungsszenarien keine analogen Ergebnisse erzeugen. Beispielsweise kann sich die Reihenfolge der untergeordneten <xref:System.Windows.Controls.DockPanel> Elemente auf <xref:System.Windows.Controls.StackPanel>ihre Größe in einer, aber nicht in auswirken. Dies <xref:System.Windows.Controls.StackPanel> liegt daran, dass Maßnahmen <xref:System.Double.PositiveInfinity>in <xref:System.Windows.Controls.DockPanel> Richtung Stapeln bei , während nur die verfügbare Größe misst.  
  
 Im folgenden Beispiel wird dieser Hauptunterschied veranschaulicht.  
  
 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 Der Unterschied im Renderingverhalten wird auf diesem Bild abgebildet.  
  
 ![Bildschirmabbildung: StackPanel im Vergleich zu DockPanel](./media/layout-smiley-stackpanel.PNG "layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>Definieren und Verwenden eines StackPanels  
 Im folgenden Beispiel wird <xref:System.Windows.Controls.StackPanel> veranschaulicht, wie Sie eine verwenden, um einen Satz vertikal positionierter Schaltflächen zu erstellen. Legen Sie für <xref:System.Windows.Controls.StackPanel.Orientation%2A> die <xref:System.Windows.Controls.Orientation.Horizontal>horizontale Positionierung die Eigenschaft auf .  
  
 [!code-csharp[StackPanel_ovw2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Ein typisches StackPanel-Element.](./media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet auch eine <xref:System.Windows.Controls.StackPanel> Variation des Elements, das datengebundene untergeordnete Inhalte automatisch "virtualisiert". In diesem Zusammenhang bezieht sich das Wort „virtualisieren“ auf eine Technik, mit der eine Teilmenge von Elementen aus einer größeren Menge von Datenelementen generiert wird, je nachdem, welche Elemente auf dem Bildschirm sichtbar sind. Es ist sowohl für den Arbeitsspeicher als auch für den Prozessor sehr aufwändig, eine große Menge an UI-Elementen zu generieren, wenn sich möglicherweise nur sehr wenige Elemente zu einer angegebenen Zeit auf einem Bildschirm befinden. <xref:System.Windows.Controls.VirtualizingStackPanel>(durch die <xref:System.Windows.Controls.VirtualizingPanel>von bereitgestellte Funktionalität) berechnet <xref:System.Windows.Controls.ItemContainerGenerator> sichtbare Elemente und arbeitet mit dem von einem <xref:System.Windows.Controls.ItemsControl> (z. B. <xref:System.Windows.Controls.ListBox> oder <xref:System.Windows.Controls.ListView>), um nur Elemente für sichtbare Elemente zu erstellen.  
  
 Das <xref:System.Windows.Controls.VirtualizingStackPanel> Element wird automatisch als Elementhost für <xref:System.Windows.Controls.ListBox>Steuerelemente wie die festgelegt. Beim Hosten einer datengebundenen Sammlung wird der Inhalt automatisch virtualisiert, <xref:System.Windows.Controls.ScrollViewer>solange sich der Inhalt innerhalb der Grenzen einer befindet. Dies verbessert erheblich die Leistung beim Hosten vieler untergeordneter Elemente.  
  
 Das folgende Markup veranschaulicht, <xref:System.Windows.Controls.VirtualizingStackPanel> wie ein als Elementhost verwendet wird. Die <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty?displayProperty=nameWithType> angefügte Eigenschaft `true` muss auf (Standard) festgelegt werden, damit die Virtualisierung erfolgt.  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel>wird verwendet, um untergeordnete Elemente in sequenzieller Position von links nach rechts zu positionieren und den Inhalt in die nächste Zeile zu brechen, wenn er den Rand des übergeordneten Containers erreicht. Inhalt kann horizontal oder vertikal ausgerichtet werden. <xref:System.Windows.Controls.WrapPanel>ist nützlich für [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] einfache fließende Szenarien. Es kann auch verwendet werden, um eine einheitliche Größe auf alle untergeordneten Elemente anzuwenden.  
  
 Im folgenden Beispiel wird <xref:System.Windows.Controls.WrapPanel> veranschaulicht, <xref:System.Windows.Controls.Button> wie Sie eine zum Anzeigen von Steuerelementen erstellen, die umbrochen werden, wenn sie den Rand ihres Containers erreichen.  
  
 [!code-cpp[WrapPanel_Intro#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](~/samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Ein typisches WrapPanel-Element.](./media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>
## <a name="nested-panel-elements"></a>Geschachtelte Panel-Elemente  
 <xref:System.Windows.Controls.Panel>Elemente können ineinander verschachtelt werden, um komplexe Layouts zu erzeugen. Dies kann sich in <xref:System.Windows.Controls.Panel> Situationen als sehr nützlich [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]erweisen, in denen man ideal für [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]einen Teil von a ist, aber möglicherweise nicht die Bedürfnisse eines anderen Teils der .  
  
 Es gibt praktisch keine Begrenzung hinsichtlich des Grads der Schachtelung, die Ihre Anwendung unterstützen kann; es wird jedoch im Allgemeinen empfohlen, Ihre Anwendung nur diese Bereichen verwenden zu lassen, die für das gewünschte Layout tatsächlich erforderlich sind. In vielen Fällen <xref:System.Windows.Controls.Grid> kann ein Element anstelle von verschachtelten Bereichen aufgrund seiner Flexibilität als Layoutcontainer verwendet werden. Dies kann die Leistung der Anwendung erhöhen, da sich keine unnötigen Elemente in Ihrer Struktur befinden.  
  
 Im folgenden Beispiel wird [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] veranschaulicht, wie Sie <xref:System.Windows.Controls.Panel> ein erstellen, das verschachtelte Elemente nutzt, um ein bestimmtes Layout zu erreichen. In diesem speziellen <xref:System.Windows.Controls.DockPanel> Fall wird ein [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Element verwendet, <xref:System.Windows.Controls.StackPanel> um <xref:System.Windows.Controls.Grid>Struktur bereitzustellen, und verschachtelte Elemente, a und a <xref:System.Windows.Controls.Canvas> werden verwendet, um untergeordnete Elemente genau innerhalb des übergeordneten <xref:System.Windows.Controls.DockPanel>Elements zu positionieren.  
  
 [!code-csharp[Nested_Panels#1](~/samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Eine UI, die verschachtelte Bereiche nutzt.](./media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>
## <a name="custom-panel-elements"></a>Benutzerdefinierte Panel-Elemente  
 Während [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein Array von flexiblen Layoutsteuerelementen bietet, können benutzerdefinierte Layoutverhalten auch durch Überschreiben der <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> und <xref:System.Windows.FrameworkElement.MeasureOverride%2A> Methoden erreicht werden. Sie können eine benutzerdefinierte Größe und Position erzielen, indem Sie innerhalb der Methode zum Außerkraftsetzen neues Postionierungsverhalten definieren.  
  
 Ebenso können benutzerdefinierte Layoutverhalten, die <xref:System.Windows.Controls.Canvas> auf <xref:System.Windows.Controls.Grid>abgeleiteten Klassen (z. B. oder ) basieren, durch Überschreiben ihrer <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> und <xref:System.Windows.FrameworkElement.MeasureOverride%2A> Methoden definiert werden.  
  
 Das folgende Markup veranschaulicht, <xref:System.Windows.Controls.Panel> wie ein benutzerdefiniertes Element erstellt wird. Diese <xref:System.Windows.Controls.Panel>neue , `PlotPanel`definiert als , unterstützt die Positionierung von untergeordneten Elementen durch die Verwendung von hartcodierten *x-* und *y-Koordinaten.* In diesem Beispiel <xref:System.Windows.Shapes.Rectangle> wird ein Element (nicht dargestellt) am Plotpunkt 50 (*x*) und 50 (*y*) positioniert.  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 Eine komplexere Implementierung von benutzerdefinierten Panel finden Sie unter [Create a Custom Content-Wrapping Panel Sample (Beispiel für das Erstellen eines Panels zum Umschließen von Inhalt)](https://go.microsoft.com/fwlink/?LinkID=159979).  
  
<a name="Panels_global_localization"></a>
## <a name="localizationglobalization-support"></a>Unterstützung der Lokalisierung/Globalisierung  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt eine Reihe von Funktionen, die Ihnen beim Erstellen einer lokalisierbaren [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] helfen.  
  
 Alle Bedienfeldelemente unterstützen <xref:System.Windows.FrameworkElement.FlowDirection%2A> die Eigenschaft nativ, die zum dynamischen Re-Flow von Inhalten basierend auf den Gebietsschema- oder Spracheinstellungen eines Benutzers verwendet werden kann. Weitere Informationen finden Sie unter <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 Die <xref:System.Windows.Window.SizeToContent%2A> Eigenschaft stellt einen Mechanismus bereit, mit dem [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]Anwendungsentwickler die Anforderungen von lokalisierten . Wenn <xref:System.Windows.SizeToContent.WidthAndHeight> Sie den Wert dieser <xref:System.Windows.Window> Eigenschaft verwenden, wird die Größe eines übergeordneten Elements immer dynamisch an den Inhalt angepasst und ist nicht durch Einschränkungen der künstlichen Höhe oder Breite eingeschränkt.  
  
 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>und <xref:System.Windows.Controls.StackPanel> sind alle gute Optionen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]für lokalisierbare . <xref:System.Windows.Controls.Canvas>ist jedoch keine gute Wahl, da es Inhalte absolut positioniert, was es schwierig macht, zu lokalisieren.  
  
 Weitere Informationen zum [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Erstellen von Anwendungen mit lokalisierbaren Benutzeroberflächen (UIs) finden Sie unter Verwenden der Übersicht über [automatische s.](../advanced/use-automatic-layout-overview.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [Beispiel für einen WPF-Layoutkatalog](https://go.microsoft.com/fwlink/?LinkID=160054)
- [Layout](../advanced/layout.md)
- [Beispiel für WPF-Steuerelementsammlungen](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
- [Übersicht über Alignment, Margin und Padding](../advanced/alignment-margins-and-padding-overview.md)
- [Create a Custom Content-Wrapping Panel Sample (Beispiel für das Erstellen eines Panels zum Umschließen von Inhalt)](https://go.microsoft.com/fwlink/?LinkID=159979)
- [Übersicht über angefügte Eigenschaften](../advanced/attached-properties-overview.md)
- [Übersicht über die Verwendung eines automatischen Layouts](../advanced/use-automatic-layout-overview.md)
- [Layout und Entwurf](../advanced/optimizing-performance-layout-and-design.md)
