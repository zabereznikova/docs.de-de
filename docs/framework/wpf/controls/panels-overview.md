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
ms.openlocfilehash: 2648296d01f0e237847fc16535b01dbd8e9c5b62
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377219"
---
# <a name="panels-overview"></a>Übersicht über Panel-Elemente
<xref:System.Windows.Controls.Panel> -Elemente sind Komponenten, die das Rendern von Elementen steuern – ihre Größe und Dimensionen, deren Position und die Anordnung des untergeordneten Inhalts. Die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet eine Reihe von vordefinierten <xref:System.Windows.Controls.Panel> Elementen sowie die Möglichkeit zum Erstellen von benutzerdefinierten <xref:System.Windows.Controls.Panel> Elemente.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Die Panel-Klasse](#Panels_view_from_10000_feet)  
  
-   [Allgemeine Member von Panel-Elementen](#Panels_declared_members)  
  
-   [Abgeleitete Panel-Elemente](#Panels_derived_elements)  
  
-   [Panels der Benutzeroberfläche](#Panels_main_UI_elements)  
  
-   [Geschachtelte Panel-Elemente](#Panels_nested_panel_elements)  
  
-   [Benutzerdefinierte Panel-Elemente](#Panels_custom_panel_elements)  
  
-   [Unterstützung für Lokalisierung/Globalisierung](#Panels_global_localization)  
  
<a name="Panels_view_from_10000_feet"></a>   
## <a name="the-panel-class"></a>Die Panel-Klasse  
 <xref:System.Windows.Controls.Panel> ist die Basisklasse für alle Elemente, die Bereitstellung Layouts in unterstützen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Abgeleitete <xref:System.Windows.Controls.Panel> Elemente werden verwendet, um die Positionierung und Anordnung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und Code.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält eine umfassende Auflistung abgeleiteter Panelimplementierungen, die komplexe Layouts zulassen. Diese abgeleiteten Klassen machen Eigenschaften und Methoden verfügbar, die die meisten [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Standardszenarios zulassen. Entwickler, die nicht gefunden wird, kein untergeordnetes Anordnungsverhalten, die ihre Anforderungen erfüllt, kann neue Layouts erstellen, durch Überschreiben der <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> und <xref:System.Windows.FrameworkElement.MeasureOverride%2A> Methoden. Weitere Informationen über das Verhalten benutzerdefinierter Layouts finden Sie unter [Benutzerdefinierte Panel-Elemente](#Panels_custom_panel_elements).  
  
<a name="Panels_declared_members"></a>   
## <a name="panel-common-members"></a>Allgemeine Panel-Elemente  
 Alle <xref:System.Windows.Controls.Panel> Elemente unterstützen die Basis größenanpassung und Positionierung von definierte Eigenschaften <xref:System.Windows.FrameworkElement>, einschließlich <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, und <xref:System.Windows.FrameworkElement.LayoutTransform%2A>. Weitere Informationen zur Positionierung von definierten Eigenschaften <xref:System.Windows.FrameworkElement>, finden Sie unter [Alignment, Margin und Padding Overview](../advanced/alignment-margins-and-padding-overview.md).  
  
 <xref:System.Windows.Controls.Panel> Stellt zusätzliche Eigenschaften, die zum verstehen und Verwenden von Layout besonders wichtig sind. Die <xref:System.Windows.Controls.Panel.Background%2A> Eigenschaft wird zum Ausfüllen des Bereichs zwischen Begrenzungen eines abgeleiteten Panel-Elements mit einem <xref:System.Windows.Media.Brush>. <xref:System.Windows.Controls.Panel.Children%2A> Stellt die Auflistung der untergeordneten Elemente dar, die die <xref:System.Windows.Controls.Panel> besteht. <xref:System.Windows.Controls.Panel.InternalChildren%2A> Stellt den Inhalt der <xref:System.Windows.Controls.Panel.Children%2A> -Auflistung plus die Member, die durch Datenbindung generiert. Beide bestehen aus einem <xref:System.Windows.Controls.UIElementCollection> untergeordneter Elemente, die innerhalb des übergeordneten Elements gehostet <xref:System.Windows.Controls.Panel>.  
  
 Im Bereich auch macht eine <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> angefügten Eigenschaft, die verwendet werden kann, um überlappende Reihenfolge in einer abgeleiteten zu erreichen <xref:System.Windows.Controls.Panel>. Mitglieder des Panels <xref:System.Windows.Controls.Panel.Children%2A> Sammlung mit einer höheren <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> Wert angezeigt werden, vor denen mit einem niedrigeren <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> Wert. Dies ist besonders für Panels wie <xref:System.Windows.Controls.Canvas> und <xref:System.Windows.Controls.Grid> , mit denen untergeordnete Elemente den gleichen koordinierten Bereich gemeinsam nutzen.  
  
 <xref:System.Windows.Controls.Panel> definiert auch die <xref:System.Windows.Controls.Panel.OnRender%2A> -Methode, die verwendet werden kann, überschreiben das Standardverhalten für die Präsentation von einem <xref:System.Windows.Controls.Panel>.  
  
#### <a name="attached-properties"></a>Angefügte Eigenschaften  
 Abgeleitete Panel-Elemente machen umfassenden Gebrauch von angefügten Eigenschaften. Eine angefügte Eigenschaft ist eine spezielle Form der Abhängigkeitseigenschaft, die nicht über die konventionelle [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Eigenschaft „Wrapper“ verfügt. Angefügte Eigenschaften haben eine besondere Syntax in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], die in einigen der folgenden Beispiele dargestellt sind.  
  
 Ein Zweck einer angefügten Eigenschaft ist es, untergeordnete Elemente zum Speichern eindeutiger Werte einer Eigenschaft zuzulassen, die eigentlich durch ein übergeordnetes Element definiert ist. Diese Anwendung dieser Funktion besitzt untergeordnete Elemente, die das übergeordnete Element darüber informieren, wie sie in [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dargestellt werden wollen, was sehr nützlich für das Anwendungslayout ist. Weitere Informationen finden Sie unter [Übersicht über angefügte Eigenschaften](../advanced/attached-properties-overview.md).  
  
<a name="Panels_derived_elements"></a>   
## <a name="derived-panel-elements"></a>Abgeleitete Panel-Elemente  
 Viele Objekte ableiten <xref:System.Windows.Controls.Panel>, aber nicht alle sind zur Verwendung als stammlayoutprovider vorgesehen. Es gibt sechs definierte Panel-Klassen (<xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel>, und <xref:System.Windows.Controls.WrapPanel>), die speziell zum Erstellen der Anwendung dienen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Jedes Panel-Element kapselt seine eigene besondere Funktionalität, wie in der folgenden Tabelle dargestellt.  
  
|Elementname|Benutzeroberflächen-Panel?|Beschreibung|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Ja|Definiert einen Bereich, in dem können Sie explizit untergeordnete Elemente von Koordinaten relativ zum Positionieren, der <xref:System.Windows.Controls.Canvas> Bereich.|  
|<xref:System.Windows.Controls.DockPanel>|Ja|Definiert einen Bereich, in dem Sie untergeordnete Elemente entweder horizontal oder vertikal relativ zueinander anordnen können.|  
|<xref:System.Windows.Controls.Grid>|Ja|Definiert einen flexiblen Rasterbereich mit Spalten und Zeilen. Untergeordnete Elemente einer <xref:System.Windows.Controls.Grid> können präzise mithilfe positioniert werden die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft.|  
|<xref:System.Windows.Controls.StackPanel>|Ja|Ordnet untergeordnete Elemente in einer einzelnen Zeile an, die horizontal oder vertikal ausgerichtet werden kann.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|Nein|Behandelt das Layout der Registerschaltflächen in einem <xref:System.Windows.Controls.TabControl>.|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|Nein|Ordnet Inhalt innerhalb einer <xref:System.Windows.Controls.ToolBar> Steuerelement.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|Nein|<xref:System.Windows.Controls.Primitives.UniformGrid> wird verwendet, um untergeordnete Elemente in einem Raster mit allen gleichen Zellengrößen anzuordnen.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|Nein|Stellt eine Basisklasse für Panels bereit, die ihre untergeordnete Auflistung „virtualisieren“ kann.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|Ja|Ordnet Inhalt an und virtualisiert ihn in einer einzelnen Zeile, die horizontal oder vertikal ausgerichtet werden kann.|  
|<xref:System.Windows.Controls.WrapPanel>|Ja|<xref:System.Windows.Controls.WrapPanel> Positioniert untergeordnete Elemente nacheinander von links nach rechts und umbricht den Inhalt in die nächste Zeile am Rand des enthaltenden Felds. Die nachfolgende Sortierung erfolgt von oben nach unten oder von rechts nach links, abhängig vom Wert der <xref:System.Windows.Controls.WrapPanel.Orientation%2A> Eigenschaft.|  
  
<a name="Panels_main_UI_elements"></a>   
## <a name="user-interface-panels"></a>Panels der Benutzeroberfläche  
 Es gibt sechs Panel-Klassen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] optimiert sind zur Unterstützung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Szenarien: <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel>, und <xref:System.Windows.Controls.WrapPanel>. Diese Panel-Elemente sind einfach zu verwenden und vielseitig und erweiterbar genug für die meisten Anwendungen.  
  
 Jeder abgeleitete <xref:System.Windows.Controls.Panel> -Element behandelt größeneinschränkungen anders. Grundlegendes zu wie eine <xref:System.Windows.Controls.Panel> Handles-Einschränkungen in horizontaler bzw. vertikaler Richtung möglich Layout besser vorhersagbar.  
  
|**Panelname**|**X-Dimension**|**Y-Dimension**|  
|--------------------|----------------------|----------------------|  
|<xref:System.Windows.Controls.Canvas>|Eingeschränkt auf Inhalt|Eingeschränkt auf Inhalt|  
|<xref:System.Windows.Controls.DockPanel>|Beschränkt|Beschränkt|  
|<xref:System.Windows.Controls.StackPanel> (Vertikale Ausrichtung)|Beschränkt|Eingeschränkt auf Inhalt|  
|<xref:System.Windows.Controls.StackPanel> (Horizontale Ausrichtung)|Eingeschränkt auf Inhalt|Beschränkt|  
|<xref:System.Windows.Controls.Grid>|Beschränkt|Beschränkt, außer in Fällen, in denen <xref:System.Windows.GridUnitType.Auto> gelten für Zeilen und Spalten|  
|<xref:System.Windows.Controls.WrapPanel>|Eingeschränkt auf Inhalt|Eingeschränkt auf Inhalt|  
  
 Eine ausführlichere Beschreibung und Verwendungsbeispiele für jedes dieser Elemente finden Sie weiter unten.  
  
<a name="Panels_overview_Canvas_subsection"></a>   
### <a name="canvas"></a>Canvas  
 Die <xref:System.Windows.Controls.Canvas> Element ermöglicht die Positionierung des Inhalts entsprechend der absoluten *x-* und *y -* Koordinaten. Elemente können in einer eindeutigen Position gezeichnet werden; alternativ bestimmt die Reihenfolge, in der Sie im Markup erscheinen, die Reihenfolge, in der die Elemente gezeichnet werden, wenn Elemente die gleichen Koordinaten verwenden.  
  
 <xref:System.Windows.Controls.Canvas> bietet die flexibelsten layoutunterstützung aller <xref:System.Windows.Controls.Panel>. Eigenschaften für Höhe und Breite werden verwendet, um den Bereich des Zeichenbereichs definieren, und Elemente in absoluten Koordinaten relativ zum Bereich des übergeordneten Elements zugewiesen <xref:System.Windows.Controls.Canvas>. Vier angefügte Eigenschaften <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType> und <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=nameWithType>, lassen die genaue Kontrolle der objektplatzierung innerhalb einer <xref:System.Windows.Controls.Canvas>, sodass den Entwickler zu positionieren und anzuordnen Elemente präzise auf dem Bildschirm.  
  
#### <a name="cliptobounds-within-a-canvas"></a>ClipToBounds innerhalb eines Canvas  
 <xref:System.Windows.Controls.Canvas> an einer beliebigen Position auf dem Bildschirm auch auf Koordinaten, die außerhalb der eigenen definierten sind untergeordnete Elemente positionieren können <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A>. Darüber hinaus <xref:System.Windows.Controls.Canvas> wird nicht von der Größe der untergeordneten Elemente beeinflusst. Daher ist es möglich, dass ein untergeordnetes Element mit anderen Elementen außerhalb des umgebenden Rechtecks des übergeordneten Elements zu überzeichnen <xref:System.Windows.Controls.Canvas>. Das Standardverhalten einer <xref:System.Windows.Controls.Canvas> besteht darin, untergeordnete Elemente außerhalb der Grenzen des übergeordneten Elements gezeichnet werden können <xref:System.Windows.Controls.Canvas>. Wenn dieses Verhalten nicht erwünscht ist, ist die <xref:System.Windows.UIElement.ClipToBounds%2A> Eigenschaft kann festgelegt werden, um `true`. Dies bewirkt, dass <xref:System.Windows.Controls.Canvas> abzuschneidenden seine eigene Größe. <xref:System.Windows.Controls.Canvas> ist das einzige Layoutelement, mit der untergeordneten Elemente außerhalb seiner Grenzen gezeichnet werden kann.  
  
 Diese Verhalten wird grafisch im [Width Properties Comparison Sample (Beispiel des Vergleich der Width-Eigenschaften)](https://go.microsoft.com/fwlink/?LinkID=160050) dargestellt.  
  
#### <a name="defining-and-using-a-canvas"></a>Definieren und Verwenden eines Canvas  
 Ein <xref:System.Windows.Controls.Canvas> kann instanziiert werden, indem Sie einfach [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oder Code. Im folgenden Beispiel wird veranschaulicht, wie <xref:System.Windows.Controls.Canvas> auf Inhalt absolut zu positionieren. Dieser Code erzeugt drei 100-Pixel-Quadrate. Das erste Quadrat ist rot, und die obere linke Position (*x, y*) ist als (0, 0) festgelegt. Das zweite Quadrat ist grün, und die obere linke Position ist (100, 100), direkt unterhalb und rechts vom ersten Quadrat. Das dritte Quadrat ist blau, und die obere linke Position ist (50, 50), daher umfasst es den unteren rechten Quadranten des ersten Quadrats und den oberen linken Quadranten des zweiten. Da das dritte Quadrat zuletzt angeordnet wird, erscheint es als obenliegend – das bedeutet, dass die überlappenden Teile die Farbe des dritten Quadrats annehmen.  
  
 [!code-csharp[CanvasOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Ein typisches Canvas-Element. ](./media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>   
### <a name="dockpanel"></a>DockPanel  
 Die <xref:System.Windows.Controls.DockPanel> -Element verwendet die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> angefügte Eigenschaft festgelegt, in den untergeordneten Inhaltselementen um Inhalt an den Rändern eines Containers zu positionieren. Wenn <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> nastaven NA hodnotu <xref:System.Windows.Controls.Dock.Top> oder <xref:System.Windows.Controls.Dock.Bottom>, es untergeordnete Elemente über- oder untereinander positioniert. Wenn <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> nastaven NA hodnotu <xref:System.Windows.Controls.Dock.Left> oder <xref:System.Windows.Controls.Dock.Right>, untergeordnete Elemente nach links oder rechts auf der jeweils anderen positioniert. Die <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> -Eigenschaft bestimmt die Position des letzten Elements hinzugefügt, als untergeordnetes Element eine <xref:System.Windows.Controls.DockPanel>.  
  
 Sie können <xref:System.Windows.Controls.DockPanel> um eine Gruppe von verwandten Steuerelementen, z. B. eine Reihe von Schaltflächen zu positionieren. Alternativ können Sie sie verwenden, um ein „gerastertes“ [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Element zu erstellen, ähnlich wie das in [!INCLUDE[TLA#tla_outlook](../../../../includes/tlasharptla-outlook-md.md)].  
  
#### <a name="sizing-to-content"></a>Anpassen der Größe an Inhalt  
 Wenn die <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A> keine Eigenschaften angegeben sind, <xref:System.Windows.Controls.DockPanel> Größe dem Inhalt. Die Größe kann sich erhöhen oder verringern, um die Größe der untergeordneten Elemente aufnehmen zu können. Allerdings auf, wenn diese Eigenschaften angegeben sind und es ist nicht mehr genügend Platz für das nächste Element des angegebenen untergeordneten, <xref:System.Windows.Controls.DockPanel> dieses untergeordnete Element und die folgenden untergeordneten Elemente nicht an und misst auch keine folgenden untergeordneten Elemente.  
  
#### <a name="lastchildfill"></a>LastChildFill  
 Standardmäßig ist das letzte untergeordnete Element von einem <xref:System.Windows.Controls.DockPanel> Element "füllt" den verbleibenden, verfügbaren Speicherplatz. Wenn dieses Verhalten nicht gewünscht ist, legen Sie die <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> Eigenschaft `false`.  
  
#### <a name="defining-and-using-a-dockpanel"></a>Definieren und Verwenden von DockPanel  
 Das folgende Beispiel zeigt, wie Sie mithilfe von Speicherplatz zu partitionieren einer <xref:System.Windows.Controls.DockPanel>. Fünf <xref:System.Windows.Controls.Border> Elemente werden als untergeordnete Elemente eines übergeordneten Elements hinzugefügt <xref:System.Windows.Controls.DockPanel>. Jede eine andere Positionierungseigenschaft verwendet eine <xref:System.Windows.Controls.DockPanel> zum datenträgerpartitions-Speicherplatz. Das letzte Element „füllt“ den verbleibenden, nicht zugeordneten Platz.  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Ein typisches DockPanel-Szenario.](./media/panel-intro-dockpanel.PNG "Panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>   
### <a name="grid"></a>Raster  
 Die <xref:System.Windows.Controls.Grid> -Element vereint die Funktionalität der absolute Positionierung und eines Steuerelements für Tabellendaten. Ein <xref:System.Windows.Controls.Grid> können Sie Elemente leicht positionieren und formatieren. <xref:System.Windows.Controls.Grid> können Sie flexible Zeilen- und spaltengruppierungen definieren, und bietet sogar einen Mechanismus zum Teilen von Größeninformationen zwischen mehreren <xref:System.Windows.Controls.Grid> Elemente.  
  
#### <a name="how-is-grid-different-from-table"></a>Wie unterscheidet sich Grid von Table?  
 <xref:System.Windows.Documents.Table> und <xref:System.Windows.Controls.Grid> haben einige allgemeine Funktionen gemeinsam, aber jede für verschiedene Szenarien am besten geeignet ist. Ein <xref:System.Windows.Documents.Table> für die Verwendung innerhalb von fortlaufendem Inhalten vorgesehen (finden Sie unter [Übersicht über Flussdokumente](../advanced/flow-document-overview.md) Weitere Informationen zum fortlaufenden Inhalt). Raster eignen sich am besten für den Einsatz in Formularen (also eigentlich überall dort, wo es keinen fortlaufenden Inhalt gibt). Innerhalb einer <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> unterstützt flow Verhalten wie Paginierung, Spaltenumbruch und Inhaltsauswahl, während eine <xref:System.Windows.Controls.Grid> nicht. Ein <xref:System.Windows.Controls.Grid> auf der anderen Seite ist außerhalb des am besten verwendet eine <xref:System.Windows.Documents.FlowDocument> vielen Gründen <xref:System.Windows.Controls.Grid> fügt Elemente basierend auf einem Zeilen- und Spaltenindexes <xref:System.Windows.Documents.Table> nicht. Die <xref:System.Windows.Controls.Grid> Element ermöglicht die Überlagerung von untergeordnetem Inhalt, sodass mehr als ein Element in einer einzelnen "Zelle" enthalten sein können <xref:System.Windows.Documents.Table> unterstützt die Überlagerung nicht. Untergeordnete Elemente einer <xref:System.Windows.Controls.Grid> können absolut zum Bereich ihrer "zellenbegrenzungen" positioniert werden. <xref:System.Windows.Documents.Table> Dieses Feature wird nicht unterstützt werden. Zum Schluss eine <xref:System.Windows.Controls.Grid> ist leichter als ein <xref:System.Windows.Documents.Table>.  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>Größenanpassungsverhalten von Spalten und Zeilen  
 Spalten und Zeilen, die definiert, die innerhalb einer <xref:System.Windows.Controls.Grid> profitieren von <xref:System.Windows.GridUnitType.Star> größenanpassung, um den verbleibenden Platz proportional zu verteilen. Wenn <xref:System.Windows.GridUnitType.Star> als die Höhe oder Breite einer Zeile oder Spalte, dass die Spalte oder Zeile eine gewichtete Proportion des verbleibenden verfügbaren Platzes empfängt ausgewählt ist. Dies steht im Gegensatz zum <xref:System.Windows.GridUnitType.Auto>, verteilt der Platz gleichmäßig nach der Größe des Inhalts in einer Spalte oder Zeile. Dieser Wert wird als `*` oder `2*` ausgedrückt, wenn [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] verwendet wird. Im ersten Fall würde die Zeile oder Spalte den verfügbaren Platz einmal erhalten, im zweiten Fall zweimal, usw. Durch die Kombination dieser Technik mit proportional zu verteilen einer <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Wert `Stretch` es ist möglich, den Layoutplatz nach dem Prozentsatz der Platz auf dem Bildschirm. <xref:System.Windows.Controls.Grid> ist der einzige Layoutbereich, der Platz auf diese Weise verteilen kann.  
  
#### <a name="defining-and-using-a-grid"></a>Definieren und Verwenden eines Rasters  
 Das folgende Beispiel veranschaulicht das Erstellen eines [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Elements, das dem Element im Dialogfeld „Ausführen“ im [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]-Startmenü ähnelt.  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Ein typisches Grid-Element.](./media/avalon-run-dialog.PNG "Avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>   
### <a name="stackpanel"></a>StackPanel  
 Ein <xref:System.Windows.Controls.StackPanel> ermöglicht es Ihnen, "Elemente in einer zugewiesenen Richtung stapeln". Die Standardrichtung eines Stapels ist vertikal. Die <xref:System.Windows.Controls.StackPanel.Orientation%2A> Eigenschaft kann verwendet werden, um fortlaufenden Inhalt zu steuern.  
  
#### <a name="stackpanel-vs-dockpanel"></a>StackPanel vs. DockPanel  
 Obwohl <xref:System.Windows.Controls.DockPanel> können auch "Stapeln" untergeordnete Elemente <xref:System.Windows.Controls.DockPanel> und <xref:System.Windows.Controls.StackPanel> medianfiltern erzeugen keine analogen Ergebnisse in manchen Szenarios. Beispielsweise kann die Reihenfolge der untergeordneten Elemente beeinflussen ihre Größe in eine <xref:System.Windows.Controls.DockPanel> jedoch nicht in einem <xref:System.Windows.Controls.StackPanel>. Grund hierfür ist, <xref:System.Windows.Controls.StackPanel> Measures in der Richtung des Stapels bei <xref:System.Double.PositiveInfinity>hingegen <xref:System.Windows.Controls.DockPanel> misst nur die verfügbare Größe.  
  
 Im folgenden Beispiel wird dieser Hauptunterschied veranschaulicht.  
  
 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 Der Unterschied im Renderingverhalten wird auf diesem Bild abgebildet.  
  
 ![Screenshot: StackPanel vs. DockPanel Screenshot](./media/layout-smiley-stackpanel.PNG "Layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>Definieren und Verwenden eines StackPanels  
 Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Windows.Controls.StackPanel> erstellen Sie eine Reihe von Schaltflächen vertikal positioniert. Legen Sie für die horizontale Positionierung die <xref:System.Windows.Controls.StackPanel.Orientation%2A> Eigenschaft <xref:System.Windows.Controls.Orientation.Horizontal>.  
  
 [!code-csharp[StackPanel_ovw2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Ein typisches StackPanel-Element.](./media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>   
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet außerdem eine Variante der <xref:System.Windows.Controls.StackPanel> -Element, das automatisch datengebundenen untergeordneten Inhalt "virtualisiert". In diesem Zusammenhang bezieht sich das Wort „virtualisieren“ auf eine Technik, mit der eine Teilmenge von Elementen aus einer größeren Menge von Datenelementen generiert wird, je nachdem, welche Elemente auf dem Bildschirm sichtbar sind. Es ist sowohl für den Arbeitsspeicher als auch für den Prozessor sehr aufwändig, eine große Menge an UI-Elementen zu generieren, wenn sich möglicherweise nur sehr wenige Elemente zu einer angegebenen Zeit auf einem Bildschirm befinden. <xref:System.Windows.Controls.VirtualizingStackPanel> (über die Funktionalität von bereitgestellten <xref:System.Windows.Controls.VirtualizingPanel>) berechnet sichtbare Elemente und arbeitet mit der <xref:System.Windows.Controls.ItemContainerGenerator> aus einer <xref:System.Windows.Controls.ItemsControl> (z. B. <xref:System.Windows.Controls.ListBox> oder <xref:System.Windows.Controls.ListView>) nur Elemente für sichtbare Elemente zu erstellen.  
  
 Die <xref:System.Windows.Controls.VirtualizingStackPanel> Element wird automatisch festgelegt, wie die Elemente für Steuerelemente, wie z. B. hosten die <xref:System.Windows.Controls.ListBox>. Wenn eine datengebundene Auflistung gehostet wird, Inhalt wird automatisch virtualisiert, solange der Inhalt innerhalb der Grenzen ist eine <xref:System.Windows.Controls.ScrollViewer>. Dies verbessert erheblich die Leistung beim Hosten vieler untergeordneter Elemente.  
  
 Das folgende Markup veranschaulicht, wie eine <xref:System.Windows.Controls.VirtualizingStackPanel> als ElementHost. Die <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty?displayProperty=nameWithType> angefügte Eigenschaft muss festgelegt werden, um `true` (Standard) für die Virtualisierung ausgeführt.  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>   
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel> Dient zum Positionieren der untergeordneten Elemente nacheinander von links nach rechts und umbricht den Inhalt in die nächste Zeile, wenn der Rand des übergeordneten Containers erreicht. Inhalt kann horizontal oder vertikal ausgerichtet werden. <xref:System.Windows.Controls.WrapPanel> eignet sich für einfache fließende [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Szenarien. Es kann auch verwendet werden, um eine einheitliche Größe auf alle untergeordneten Elemente anzuwenden.  
  
 Im folgende Beispiel wird veranschaulicht, wie zum Erstellen einer <xref:System.Windows.Controls.WrapPanel> anzuzeigende <xref:System.Windows.Controls.Button> Steuerelemente, die umschlossen wird, wenn sie den Rand ihres Containers erreichen.  
  
 [!code-cpp[WrapPanel_Intro#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](~/samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Ein typisches WrapPanel-Element.](./media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>   
## <a name="nested-panel-elements"></a>Geschachtelte Panel-Elemente  
 <xref:System.Windows.Controls.Panel> -Elemente können ineinander geschachtelt werden, um komplexe Layouts zu erzeugen. Dies kann sehr nützlich in Situationen, bei denen ein Beweisen <xref:System.Windows.Controls.Panel> eignet sich ideal für einen Teil des eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], aber nicht die Anforderungen eines anderen Teils der entsprechen möglicherweise die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Es gibt praktisch keine Begrenzung hinsichtlich des Grads der Schachtelung, die Ihre Anwendung unterstützen kann; es wird jedoch im Allgemeinen empfohlen, Ihre Anwendung nur diese Bereichen verwenden zu lassen, die für das gewünschte Layout tatsächlich erforderlich sind. In vielen Fällen eine <xref:System.Windows.Controls.Grid> -Element anstelle von geschachtelten Bereichen aufgrund seiner Flexibilität als Layoutcontainer verwendet werden kann. Dies kann die Leistung der Anwendung erhöhen, da sich keine unnötigen Elemente in Ihrer Struktur befinden.  
  
 Im folgende Beispiel wird veranschaulicht, wie zum Erstellen einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] geschachtelten nutzt, <xref:System.Windows.Controls.Panel> Elemente, um ein bestimmtes Layout zu erzielen. In diesem Fall eine <xref:System.Windows.Controls.DockPanel> Element dient zur Bereitstellung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] -Struktur und geschachtelte <xref:System.Windows.Controls.StackPanel> Elemente eine <xref:System.Windows.Controls.Grid>, und ein <xref:System.Windows.Controls.Canvas> werden verwendet, um untergeordnete Elemente genau im übergeordneten Element positioniert <xref:System.Windows.Controls.DockPanel>.  
  
 [!code-csharp[Nested_Panels#1](~/samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Eine UI, die verschachtelte Bereiche nutzt.](./media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>   
## <a name="custom-panel-elements"></a>Benutzerdefinierte Panel-Elemente  
 Während [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet eine Reihe von flexiblen Layoutsteuerelementen, benutzerdefiniertes Layout-Verhalten auch werden, durch Überschreiben erreicht können der <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> und <xref:System.Windows.FrameworkElement.MeasureOverride%2A> Methoden. Sie können eine benutzerdefinierte Größe und Position erzielen, indem Sie innerhalb der Methode zum Außerkraftsetzen neues Postionierungsverhalten definieren.  
  
 Auf ähnliche Weise benutzerdefiniertes Layoutverhalten basierend auf abgeleiteten Klassen (z. B. <xref:System.Windows.Controls.Canvas> oder <xref:System.Windows.Controls.Grid>) definiert werden, indem Sie überschreiben die <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> und <xref:System.Windows.FrameworkElement.MeasureOverride%2A> Methoden.  
  
 Das folgende Markup veranschaulicht, wie eine benutzerdefinierte <xref:System.Windows.Controls.Panel> Element. Diese neue <xref:System.Windows.Controls.Panel>, definiert als `PlotPanel`, unterstützt die Positionierung von untergeordneten Elementen durch Verwendung von hartcodierten *x-* und *y -* Koordinaten. In diesem Beispiel eine <xref:System.Windows.Shapes.Rectangle> -Element (nicht abgebildet) am Zeichnungspunkt 50 positioniert ist (*x*), und 50 (*y*).  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 Eine komplexere Implementierung von benutzerdefinierten Panel finden Sie unter [Create a Custom Content-Wrapping Panel Sample (Beispiel für das Erstellen eines Panels zum Umschließen von Inhalt)](https://go.microsoft.com/fwlink/?LinkID=159979).  
  
<a name="Panels_global_localization"></a>   
## <a name="localizationglobalization-support"></a>Unterstützung der Lokalisierung/Globalisierung  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt eine Reihe von Funktionen, die Ihnen beim Erstellen einer lokalisierbaren [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] helfen.  
  
 Alle Panel-Elemente nativ unterstützen die <xref:System.Windows.FrameworkElement.FlowDirection%2A> -Eigenschaft, die verwendet werden kann, um die Inhalte basierend auf Gebietsschema oder der Sprache des Benutzers dynamisch umzubrechen. Weitere Informationen finden Sie unter <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 Die <xref:System.Windows.Window.SizeToContent%2A> -Eigenschaft bietet einen Mechanismus, der Entwicklern ermöglicht, die die Anforderungen der voraussichtlich lokalisiert [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Mithilfe der <xref:System.Windows.SizeToContent.WidthAndHeight> Wert dieser Eigenschaft, ein übergeordnetes Element <xref:System.Windows.Window> immer dynamisch an Inhalt Größen und wird nicht von künstlichen Höhen- oder breitebeschränkungen eingeschränkt.  
  
 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, und <xref:System.Windows.Controls.StackPanel> sind eine gute Wahl für alle lokalisierbaren [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. <xref:System.Windows.Controls.Canvas> ist Sie jedoch nicht auf eine gute Wahl, da es Inhalt absolut positioniert und somit schwer zu lokalisieren.  
  
 Weitere Informationen zum Erstellen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen mit lokalisierbaren [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)]s finden Sie unter [Übersicht über die Verwendung eines automatischen Layouts](../advanced/use-automatic-layout-overview.md).  
  
## <a name="see-also"></a>Siehe auch
- [Exemplarische Vorgehensweise: Walkthrough: My first WPF desktop application (Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung)](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [Beispiel für einen WPF-Layoutkatalog](https://go.microsoft.com/fwlink/?LinkID=160054)
- [Layout](../advanced/layout.md)
- [Beispiel für WPF-Steuerelementsammlungen](https://go.microsoft.com/fwlink/?LinkID=160053)
- [Übersicht über Alignment, Margin und Padding](../advanced/alignment-margins-and-padding-overview.md)
- [Erstellen einer benutzerdefinierten Content-Wrapping Panel Sample](https://go.microsoft.com/fwlink/?LinkID=159979)
- [Übersicht über angefügte Eigenschaften](../advanced/attached-properties-overview.md)
- [Übersicht über die Verwendung eines automatischen Layouts](../advanced/use-automatic-layout-overview.md)
- [Layout und Entwurf](../advanced/optimizing-performance-layout-and-design.md)
