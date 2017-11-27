---
title: "Übersicht über Panel-Elemente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF], about Panel control
- controls [WPF], Panel
ms.assetid: f73644af-9941-4611-8754-6d4cef03fc44
caps.latest.revision: "48"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f89ea3308d0e6cffc3ed50809f0e87e7ba854ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="panels-overview"></a>Übersicht über Panel-Elemente
<xref:System.Windows.Controls.Panel>Elemente sind die Komponenten, die das Rendern von Elementen zu steuern, ihre Größe und Dimensionen, deren Position und die Anordnung des untergeordneten Inhalts. Die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet eine Reihe von vordefinierten <xref:System.Windows.Controls.Panel> Elemente als auch die Möglichkeit zum Erstellen von benutzerdefinierten <xref:System.Windows.Controls.Panel> Elemente.  
  
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
 <xref:System.Windows.Controls.Panel>ist die Basisklasse für alle Elemente, die Layout Bereitstellen in unterstützen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Abgeleitete <xref:System.Windows.Controls.Panel> Elemente dienen zum Positionieren und Anordnen von Elementen in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und Code.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält eine umfassende Auflistung abgeleiteter Panelimplementierungen, die komplexe Layouts zulassen. Diese abgeleiteten Klassen machen Eigenschaften und Methoden verfügbar, die die meisten [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Standardszenarios zulassen. Entwickler, die nicht gefunden wird, ein untergeordnetes Anordnung Verhalten, die ihren Bedürfnissen entspricht, kann neue Layouts erstellen, durch Überschreiben der <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> und <xref:System.Windows.FrameworkElement.MeasureOverride%2A> Methoden. Weitere Informationen über das Verhalten benutzerdefinierter Layouts finden Sie unter [Benutzerdefinierte Panel-Elemente](#Panels_custom_panel_elements).  
  
<a name="Panels_declared_members"></a>   
## <a name="panel-common-members"></a>Allgemeine Panel-Elemente  
 Alle <xref:System.Windows.Controls.Panel> Elemente unterstützen die Basis größenanpassung und Positionierung von definierte Eigenschaften <xref:System.Windows.FrameworkElement>, einschließlich <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, und <xref:System.Windows.FrameworkElement.LayoutTransform%2A>. Weitere Informationen zum Positionieren von definierte Eigenschaften <xref:System.Windows.FrameworkElement>, finden Sie unter [Padding Übersicht, Seitenränder und Ausrichtung](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md).  
  
 <xref:System.Windows.Controls.Panel>macht zusätzliche Eigenschaften, die besonders wichtig zum verstehen und Layout zu verwenden sind. Die <xref:System.Windows.Controls.Panel.Background%2A> Eigenschaft wird verwendet, um den Bereich zwischen der Grenzen eines Elements mit einem abgeleiteten Panel Füllen einer <xref:System.Windows.Media.Brush>. <xref:System.Windows.Controls.Panel.Children%2A>Stellt die Auflistung der untergeordneten Elemente dar, die die <xref:System.Windows.Controls.Panel> besteht. <xref:System.Windows.Controls.Panel.InternalChildren%2A>Stellt den Inhalt der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung plus Mitglieder von Datenbindung generiert. Beide bestehen aus einer <xref:System.Windows.Controls.UIElementCollection> untergeordneter Elemente innerhalb des übergeordneten Elements gehostet <xref:System.Windows.Controls.Panel>.  
  
 Bereich auch macht eine <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> -Eigenschaft, die verwendet werden kann, erreichen Sie überlappende Reihenfolge in einer abgeleiteten <xref:System.Windows.Controls.Panel>. Elemente eines Bereichs <xref:System.Windows.Controls.Panel.Children%2A> Auflistung mit einer höheren <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> Wert angezeigt wird, vor Abonnements mit einem niedrigeren <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> Wert. Dies ist besonders nützlich für Bereiche wie z. B. <xref:System.Windows.Controls.Canvas> und <xref:System.Windows.Controls.Grid> untergeordnete Elemente mit demselben Koordinatenbereich ermöglichen.  
  
 <xref:System.Windows.Controls.Panel>definiert auch die <xref:System.Windows.Controls.Panel.OnRender%2A> -Methode, die verwendet werden kann, überschreiben Sie das Standardverhalten für die Präsentation von einem <xref:System.Windows.Controls.Panel>.  
  
#### <a name="attached-properties"></a>Angefügte Eigenschaften  
 Abgeleitete Panel-Elemente machen umfassenden Gebrauch von angefügten Eigenschaften. Eine angefügte Eigenschaft ist eine spezielle Form der Abhängigkeitseigenschaft, die nicht über die konventionelle [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Eigenschaft „Wrapper“ verfügt. Angefügte Eigenschaften haben eine besondere Syntax in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], die in einigen der folgenden Beispiele dargestellt sind.  
  
 Ein Zweck einer angefügten Eigenschaft ist es, untergeordnete Elemente zum Speichern eindeutiger Werte einer Eigenschaft zuzulassen, die eigentlich durch ein übergeordnetes Element definiert ist. Diese Anwendung dieser Funktion besitzt untergeordnete Elemente, die das übergeordnete Element darüber informieren, wie sie in [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dargestellt werden wollen, was sehr nützlich für das Anwendungslayout ist. Weitere Informationen finden Sie unter [Übersicht über angefügte Eigenschaften](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
<a name="Panels_derived_elements"></a>   
## <a name="derived-panel-elements"></a>Abgeleitete Panel-Elemente  
 Viele Objekte ableiten <xref:System.Windows.Controls.Panel>, aber nicht alle für die Verwendung vorgesehen sind, als Root-Layout-Anbieter. Es gibt sechs definierten Bereich-Klassen (<xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel>, und <xref:System.Windows.Controls.WrapPanel>), die speziell zum Erstellen der Anwendung dienen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Jedes Panel-Element kapselt seine eigene besondere Funktionalität, wie in der folgenden Tabelle dargestellt.  
  
|Elementname|Benutzeroberflächen-Panel?|Beschreibung|  
|------------------|---------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Ja|Definiert einen Bereich, in dem können Sie explizit untergeordnete Elemente durch Koordinaten relativ zum Positionieren, der <xref:System.Windows.Controls.Canvas> Bereich.|  
|<xref:System.Windows.Controls.DockPanel>|Ja|Definiert einen Bereich, in dem Sie untergeordnete Elemente entweder horizontal oder vertikal relativ zueinander anordnen können.|  
|<xref:System.Windows.Controls.Grid>|Ja|Definiert einen flexiblen Rasterbereich mit Spalten und Zeilen. Untergeordnete Elemente von einer <xref:System.Windows.Controls.Grid> mit genau positioniert werden die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft.|  
|<xref:System.Windows.Controls.StackPanel>|Ja|Ordnet untergeordnete Elemente in einer einzelnen Zeile an, die horizontal oder vertikal ausgerichtet werden kann.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|Nein|Behandelt das Layout der Registerkartenschaltflächen in einem <xref:System.Windows.Controls.TabControl>.|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|Nein|Ordnet Inhalt innerhalb einer <xref:System.Windows.Controls.ToolBar> Steuerelement.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|Nein|<xref:System.Windows.Controls.Primitives.UniformGrid>Dient zum Anordnen von untergeordneten Elementen in einem Raster mit gleich großen Zellen.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|Nein|Stellt eine Basisklasse für Panels bereit, die ihre untergeordnete Auflistung „virtualisieren“ kann.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|Ja|Ordnet Inhalt an und virtualisiert ihn in einer einzelnen Zeile, die horizontal oder vertikal ausgerichtet werden kann.|  
|<xref:System.Windows.Controls.WrapPanel>|Ja|<xref:System.Windows.Controls.WrapPanel>Positioniert untergeordnete Elemente sequenziell von links nach rechts und wichtige Inhalt in die nächste Zeile am Rand des enthaltenden Felds. Erfolgt die nachfolgende Sortierung nacheinander von oben nach unten oder von rechts nach links, abhängig vom Wert der <xref:System.Windows.Controls.WrapPanel.Orientation%2A> Eigenschaft.|  
  
<a name="Panels_main_UI_elements"></a>   
## <a name="user-interface-panels"></a>Panels der Benutzeroberfläche  
 Es gibt sechs Panel-Klassen zur Verfügung, in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] optimiert sind zur Unterstützung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Szenarien: <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel>, und <xref:System.Windows.Controls.WrapPanel>. Diese Panel-Elemente sind einfach zu verwenden und vielseitig und erweiterbar genug für die meisten Anwendungen.  
  
 Jeder abgeleitete <xref:System.Windows.Controls.Panel> Element Sizing Einschränkungen unterschiedlich behandelt. Grundlegendes zu wie eine <xref:System.Windows.Controls.Panel> Handles Einschränkungen in horizontaler oder vertikaler Richtung möglich Layout besser vorhersagbar.  
  
|**Panelname**|**X-Dimension**|**Y-Dimension**|  
|--------------------|----------------------|----------------------|  
|<xref:System.Windows.Controls.Canvas>|Eingeschränkt auf Inhalt|Eingeschränkt auf Inhalt|  
|<xref:System.Windows.Controls.DockPanel>|Beschränkt|Beschränkt|  
|<xref:System.Windows.Controls.StackPanel>(Vertikale Ausrichtung)|Beschränkt|Eingeschränkt auf Inhalt|  
|<xref:System.Windows.Controls.StackPanel>(Horizontale Ausrichtung)|Eingeschränkt auf Inhalt|Beschränkt|  
|<xref:System.Windows.Controls.Grid>|Beschränkt|Eingeschränkt, außer in Fällen, in denen <xref:System.Windows.GridUnitType.Auto> gelten für Zeilen und Spalten|  
|<xref:System.Windows.Controls.WrapPanel>|Eingeschränkt auf Inhalt|Eingeschränkt auf Inhalt|  
  
 Eine ausführlichere Beschreibung und Verwendungsbeispiele für jedes dieser Elemente finden Sie weiter unten.  
  
<a name="Panels_overview_Canvas_subsection"></a>   
### <a name="canvas"></a>Canvas  
 Die <xref:System.Windows.Controls.Canvas> Element ermöglicht Inhalt gemäß Ihrer Absolute Positionierung *X -* und *y-*Koordinaten. Elemente können in einer eindeutigen Position gezeichnet werden; alternativ bestimmt die Reihenfolge, in der Sie im Markup erscheinen, die Reihenfolge, in der die Elemente gezeichnet werden, wenn Elemente die gleichen Koordinaten verwenden.  
  
 <xref:System.Windows.Controls.Canvas>bietet die flexibelste Layout Unterstützung aller <xref:System.Windows.Controls.Panel>. Höhen-und Breiteneigenschaften werden verwendet, um den Bereich des Zeichenbereichs definieren, und Elemente innerhalb sind absolute Koordinaten relativ zum Bereich des übergeordneten Elements zugewiesen <xref:System.Windows.Controls.Canvas>. Vier angefügten Eigenschaften <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=nameWithType> und <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=nameWithType>, ermöglichen Sie genaue Steuerung der Platzierung des Objekts innerhalb einer <xref:System.Windows.Controls.Canvas>, ermöglichen den Entwickler zu positionieren und Anordnen von Elementen, die genau auf dem Bildschirm.  
  
#### <a name="cliptobounds-within-a-canvas"></a>ClipToBounds innerhalb eines Canvas  
 <xref:System.Windows.Controls.Canvas>an einer beliebigen Position auf dem Bildschirm, selbst bei Koordinaten, die außerhalb der eigenen definierten sind untergeordnete Elemente positionieren können <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A>. Darüber hinaus <xref:System.Windows.Controls.Canvas> keinen Einfluss auf die Größe der untergeordneten Elemente. Daher ist es möglich, dass ein untergeordnetes Element, um andere Elemente außerhalb des umschließenden Rechtecks des übergeordneten Elements überzeichnet <xref:System.Windows.Controls.Canvas>. Das Standardverhalten einer <xref:System.Windows.Controls.Canvas> werden untergeordnete Elemente, die außerhalb des gültigen Bereichs des übergeordneten Elements gezeichnet werden zugelassen <xref:System.Windows.Controls.Canvas>. Wenn dieses Verhalten nicht erwünscht ist, ist die <xref:System.Windows.UIElement.ClipToBounds%2A> Eigenschaft kann festgelegt werden, um `true`. Dies bewirkt, dass <xref:System.Windows.Controls.Canvas> auf seine eigene Größe beschnitten. <xref:System.Windows.Controls.Canvas>ist die einzige Layoutelement, das untergeordnete Elemente, die sich außerhalb der Begrenzungen gezeichnet werden kann.  
  
 Diese Verhalten wird grafisch im [Width Properties Comparison Sample (Beispiel des Vergleich der Width-Eigenschaften)](http://go.microsoft.com/fwlink/?LinkID=160050) dargestellt.  
  
#### <a name="defining-and-using-a-canvas"></a>Definieren und Verwenden eines Canvas  
 Ein <xref:System.Windows.Controls.Canvas> kann instanziiert werden, indem einfach [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oder Code. Im folgenden Beispiel wird veranschaulicht, wie <xref:System.Windows.Controls.Canvas> Inhalt absolut positionieren. Dieser Code erzeugt drei 100-Pixel-Quadrate. Das erste Quadrat ist rot, und die obere linke Position (*x, y*) ist als (0, 0) festgelegt. Das zweite Quadrat ist grün, und die obere linke Position ist (100, 100), direkt unterhalb und rechts vom ersten Quadrat. Das dritte Quadrat ist blau, und die obere linke Position ist (50, 50), daher umfasst es den unteren rechten Quadranten des ersten Quadrats und den oberen linken Quadranten des zweiten. Da das dritte Quadrat zuletzt angeordnet wird, erscheint es als obenliegend – das bedeutet, dass die überlappenden Teile die Farbe des dritten Quadrats annehmen.  
  
 [!code-csharp[CanvasOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xaml[CanvasOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Ein typisches Canvas-Element. ](../../../../docs/framework/wpf/controls/media/panel-intro-canvas.PNG "panel_intro_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>   
### <a name="dockpanel"></a>DockPanel  
 Die <xref:System.Windows.Controls.DockPanel> -Element verwendet die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> angefügte Eigenschaft festgelegt untergeordnete Inhaltselemente um Inhalt an den Rändern eines Containers zu positionieren. Wenn <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> festgelegt ist, um <xref:System.Windows.Controls.Dock.Top> oder <xref:System.Windows.Controls.Dock.Bottom>, untergeordnete Elemente oberhalb oder unterhalb zueinander positioniert. Wenn <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> festgelegt ist, um <xref:System.Windows.Controls.Dock.Left> oder <xref:System.Windows.Controls.Dock.Right>, untergeordnete Elemente auf der linken Seite oder des jeweils anderen positioniert. Die <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> Eigenschaft bestimmt die Position des letzten Elements als untergeordnetes Element des hinzugefügt eine <xref:System.Windows.Controls.DockPanel>.  
  
 Sie können <xref:System.Windows.Controls.DockPanel> um eine Gruppe von verwandten Steuerelementen, z. B. eine Reihe von Schaltflächen zu positionieren. Alternativ können Sie sie verwenden, um ein „gerastertes“ [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Element zu erstellen, ähnlich wie das in [!INCLUDE[TLA#tla_outlook](../../../../includes/tlasharptla-outlook-md.md)].  
  
#### <a name="sizing-to-content"></a>Anpassen der Größe an Inhalt  
 Wenn ihre <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaften wurden nicht angegeben, <xref:System.Windows.Controls.DockPanel> Größen zum jeweiligen Inhalt. Die Größe kann sich erhöhen oder verringern, um die Größe der untergeordneten Elemente aufnehmen zu können. Jedoch auf, wenn diese Eigenschaften angegeben werden und es ist nicht mehr Platz für das nächste angegebene untergeordnete Element <xref:System.Windows.Controls.DockPanel> dieses untergeordnete Element oder die nachfolgenden untergeordneten Elemente nicht an und misst die untergeordneten Elemente nicht.  
  
#### <a name="lastchildfill"></a>LastChildFill  
 Standardmäßig ist das letzte untergeordnete Element von einer <xref:System.Windows.Controls.DockPanel> Element wird "fill" den verbleibenden verfügbaren Speicherplatz. Wenn dieses Verhalten nicht erwünscht ist, legen Sie die <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> Eigenschaft `false`.  
  
#### <a name="defining-and-using-a-dockpanel"></a>Definieren und Verwenden von DockPanel  
 Im folgenden Beispiel wird veranschaulicht, wie zum Partitionieren von Speicherplatz mit einem <xref:System.Windows.Controls.DockPanel>. Fünf <xref:System.Windows.Controls.Border> Elemente werden als untergeordnete Elemente eines übergeordneten Elements hinzugefügt <xref:System.Windows.Controls.DockPanel>. Jede verwendet eine andere Positionierungseigenschaft der eine <xref:System.Windows.Controls.DockPanel> zum datenträgerpartitions-Speicherplatz. Das letzte Element „füllt“ den verbleibenden, nicht zugeordneten Platz.  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Ein typisches DockPanel-Szenario.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "Panel_intro_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>   
### <a name="grid"></a>Raster  
 Die <xref:System.Windows.Controls.Grid> Element verbindet die Funktionalität eines absolute Positionierung und Tabellendaten-Steuerelements. Ein <xref:System.Windows.Controls.Grid> können Sie problemlos Position und des Stils Elemente. <xref:System.Windows.Controls.Grid>können Sie flexibel Zeilen- und spaltengruppierungen definieren und sogar bietet einen Mechanismus zum Freigeben von Informationen zur Größe zwischen mehreren <xref:System.Windows.Controls.Grid> Elemente.  
  
#### <a name="how-is-grid-different-from-table"></a>Wie unterscheidet sich Grid von Table?  
 <xref:System.Windows.Documents.Table>und <xref:System.Windows.Controls.Grid> haben einige allgemeine Funktionen gemeinsam, aber jede eignet sich optimal für verschiedene Szenarien. Ein <xref:System.Windows.Documents.Table> dient zur Verwendung innerhalb des fortlaufenden Inhalts (finden Sie unter [Nachrichtenfluss-Dokument (Übersicht)](../../../../docs/framework/wpf/advanced/flow-document-overview.md) für Weitere Informationen zu fortlaufendem Inhalt). Raster eignen sich am besten für den Einsatz in Formularen (also eigentlich überall dort, wo es keinen fortlaufenden Inhalt gibt). Innerhalb einer <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> unterstützt flow Content Verhalten wie die Paginierung Spalte Umfließen und Inhaltsauswahl beim eine <xref:System.Windows.Controls.Grid> hingegen nicht. Ein <xref:System.Windows.Controls.Grid> andererseits wird außerhalb der am besten verwendet eine <xref:System.Windows.Documents.FlowDocument> vielen Gründen <xref:System.Windows.Controls.Grid> fügt Elemente basierend auf einer Zeile und Spalte Index <xref:System.Windows.Documents.Table> hingegen nicht. Die <xref:System.Windows.Controls.Grid> -Element ermöglicht die Anordnung von untergeordnetem Inhalt, sodass mehr als ein Element in einer "Zelle" vorhanden sein <xref:System.Windows.Documents.Table>Ebenenstruktur unterstützt nicht. Untergeordnete Elemente von einem <xref:System.Windows.Controls.Grid> relativ zum Bereich des Umrisslinien "Zelle" absolut positioniert werden kann. <xref:System.Windows.Documents.Table>Dieses Feature wird nicht unterstützt werden. Schließlich eine <xref:System.Windows.Controls.Grid> ist weniger umfangreich als eine <xref:System.Windows.Documents.Table>.  
  
#### <a name="sizing-behavior-of-columns-and-rows"></a>Größenanpassungsverhalten von Spalten und Zeilen  
 Spalten und Zeilen, die definiert, die innerhalb einer <xref:System.Windows.Controls.Grid> nutzen <xref:System.Windows.GridUnitType.Star> anpassen, um den verbleibenden Platz proportional zu verteilen. Wenn <xref:System.Windows.GridUnitType.Star> ausgewählt ist, als die Höhe oder Breite einer Zeile oder Spalte, die Spalte oder Zeile eine gewichtete Proportion des verfügbaren Speicherplatzes erhalten. Dies steht im Gegensatz zur <xref:System.Windows.GridUnitType.Auto>, dem Speicherplatz, die gleichmäßig auf Grundlage der Größe des Inhalts in einer Spalte oder Zeile verteilt wird. Dieser Wert wird als `*` oder `2*` ausgedrückt, wenn [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] verwendet wird. Im ersten Fall würde die Zeile oder Spalte den verfügbaren Platz einmal erhalten, im zweiten Fall zweimal, usw. Durch die Kombination dieser Technik proportional Speicherplatz mit Verteilen einer <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Wert `Stretch` ist es möglich, Layout partitionsspeicherplatz um Prozentsatz der Bildschirmbereich. <xref:System.Windows.Controls.Grid>ist die einzige LayoutPanel-Element, die Leerzeichen auf diese Weise verteilen können.  
  
#### <a name="defining-and-using-a-grid"></a>Definieren und Verwenden eines Rasters  
 Das folgende Beispiel veranschaulicht das Erstellen eines [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Elements, das dem Element im Dialogfeld „Ausführen“ im [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]-Startmenü ähnelt.  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Ein typisches Grid-Element.](../../../../docs/framework/wpf/controls/media/avalon-run-dialog.PNG "Avalon_run_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>   
### <a name="stackpanel"></a>StackPanel  
 Ein <xref:System.Windows.Controls.StackPanel> ermöglicht es Ihnen, "Elemente in einer zugewiesenen Richtung stapeln". Die Standardrichtung eines Stapels ist vertikal. Die <xref:System.Windows.Controls.StackPanel.Orientation%2A> Eigenschaft kann verwendet werden, um Inhaltsfluss steuern.  
  
#### <a name="stackpanel-vs-dockpanel"></a>StackPanel vs. DockPanel  
 Obwohl <xref:System.Windows.Controls.DockPanel> können auch "aufeinander"gestapelt"untergeordnete Elemente <xref:System.Windows.Controls.DockPanel> und <xref:System.Windows.Controls.StackPanel> erzeugen keine Analog Ergebnisse in manchen Szenarien. Die Reihenfolge von untergeordneten Elementen kann z. B. ihre Größe in beeinflussen eine <xref:System.Windows.Controls.DockPanel> jedoch nicht in einem <xref:System.Windows.Controls.StackPanel>. Grund hierfür ist, <xref:System.Windows.Controls.StackPanel> Measures in Richtung stapeln an <xref:System.Double.PositiveInfinity>, wohingegen <xref:System.Windows.Controls.DockPanel> misst nur die verfügbare Größe.  
  
 Im folgenden Beispiel wird dieser Hauptunterschied veranschaulicht.  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 Der Unterschied im Renderingverhalten wird auf diesem Bild abgebildet.  
  
 ![Screenshot: StackPanel vs. DockPanel Screenshot](../../../../docs/framework/wpf/controls/media/layout-smiley-stackpanel.PNG "Layout_smiley_stackpanel")  
  
#### <a name="defining-and-using-a-stackpanel"></a>Definieren und Verwenden eines StackPanels  
 Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Windows.Controls.StackPanel> So erstellen eine Reihe von Schaltflächen vertikal positioniert. Legen Sie für die horizontale Positionierung der <xref:System.Windows.Controls.StackPanel.Orientation%2A> Eigenschaft <xref:System.Windows.Controls.Orientation.Horizontal>.  
  
 [!code-csharp[StackPanel_ovw2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Ein typisches StackPanel-Element.](../../../../docs/framework/wpf/controls/media/panel-intro-stackpanel.PNG "panel_intro_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>   
#### <a name="virtualizingstackpanel"></a>VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet auch eine Variante der <xref:System.Windows.Controls.StackPanel> -Element, das von datengebundenen untergeordneten Inhalt automatisch "virtualisiert". In diesem Zusammenhang bezieht sich das Wort „virtualisieren“ auf eine Technik, mit der eine Teilmenge von Elementen aus einer größeren Menge von Datenelementen generiert wird, je nachdem, welche Elemente auf dem Bildschirm sichtbar sind. Es ist sowohl für den Arbeitsspeicher als auch für den Prozessor sehr aufwändig, eine große Menge an UI-Elementen zu generieren, wenn sich möglicherweise nur sehr wenige Elemente zu einer angegebenen Zeit auf einem Bildschirm befinden. <xref:System.Windows.Controls.VirtualizingStackPanel>(über eine Funktionalität von bereitgestellten <xref:System.Windows.Controls.VirtualizingPanel>) sichtbaren Elemente berechnet und kann mit der <xref:System.Windows.Controls.ItemContainerGenerator> aus einer <xref:System.Windows.Controls.ItemsControl> (z. B. <xref:System.Windows.Controls.ListBox> oder <xref:System.Windows.Controls.ListView>) nur Elemente für die sichtbaren Elemente erstellen.  
  
 Die <xref:System.Windows.Controls.VirtualizingStackPanel> Element wird automatisch festgelegt, als host für die Elemente für Steuerelemente wie z. B. die <xref:System.Windows.Controls.ListBox>. Wenn eine Auflistung gehostet datengebundene, Inhalt wird automatisch virtualisiert, solange der Inhalt innerhalb der Grenzen des ist eine <xref:System.Windows.Controls.ScrollViewer>. Dies verbessert erheblich die Leistung beim Hosten vieler untergeordneter Elemente.  
  
 Das folgende Markup veranschaulicht, wie eine <xref:System.Windows.Controls.VirtualizingStackPanel> als ElementHost. Die <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizingProperty%2A?displayProperty=nameWithType> angefügte Eigenschaft muss festgelegt werden, um `true` (Standard), für die Virtualisierung ausgeführt.  
  
 [!code-xaml[VirtualizingStackPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>   
### <a name="wrappanel"></a>WrapPanel  
 <xref:System.Windows.Controls.WrapPanel>wird verwendet, um untergeordnete Elemente zu positionieren, sequenzielle Position von links nach rechts und wichtige Inhalt in die nächste Zeile, wenn er den Rand des übergeordneten Containers erreicht. Inhalt kann horizontal oder vertikal ausgerichtet werden. <xref:System.Windows.Controls.WrapPanel>eignet sich für einfache fließen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Szenarien. Es kann auch verwendet werden, um eine einheitliche Größe auf alle untergeordneten Elemente anzuwenden.  
  
 Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Windows.Controls.WrapPanel> anzuzeigenden <xref:System.Windows.Controls.Button> Steuerelemente, die umbrochen werden, wenn sie den Rand des Containers erreichen.  
  
 [!code-cpp[WrapPanel_Intro#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xaml[WrapPanel_Intro#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Ein typisches WrapPanel-Element.](../../../../docs/framework/wpf/controls/media/wrappanel-element.PNG "WrapPanel_Element")  
  
<a name="Panels_nested_panel_elements"></a>   
## <a name="nested-panel-elements"></a>Geschachtelte Panel-Elemente  
 <xref:System.Windows.Controls.Panel>Elemente können ineinander geschachtelt werden, um komplexe Layouts zu erzeugen. Dies kann sehr nützlich in Situationen, bei denen einem nachweisen <xref:System.Windows.Controls.Panel> eignet sich ideal für einen Teil einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], aber nicht die Anforderungen von einem anderen Teil des erfüllen kann die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Es gibt praktisch keine Begrenzung hinsichtlich des Grads der Schachtelung, die Ihre Anwendung unterstützen kann; es wird jedoch im Allgemeinen empfohlen, Ihre Anwendung nur diese Bereichen verwenden zu lassen, die für das gewünschte Layout tatsächlich erforderlich sind. In vielen Fällen einen <xref:System.Windows.Controls.Grid> -Element anstelle von verschachtelte Bereiche aufgrund seiner Flexibilität als Layoutcontainer verwendet werden kann. Dies kann die Leistung der Anwendung erhöhen, da sich keine unnötigen Elemente in Ihrer Struktur befinden.  
  
 Im folgenden Beispiel wird veranschaulicht, wie eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] diesen nutzt geschachtelten <xref:System.Windows.Controls.Panel> Elemente, um ein bestimmtes Layout zu erzielen. In diesem speziellen Fall ein <xref:System.Windows.Controls.DockPanel> Element wird zum Bereitstellen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] -Struktur <xref:System.Windows.Controls.StackPanel> Elemente, eine <xref:System.Windows.Controls.Grid>, und ein <xref:System.Windows.Controls.Canvas> werden verwendet, um untergeordnete Elemente genau innerhalb des übergeordneten Elements positioniert <xref:System.Windows.Controls.DockPanel>.  
  
 [!code-csharp[Nested_Panels#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 Die kompilierte Anwendung gibt ein neues [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aus, das folgendermaßen aussieht.  
  
 ![Eine UI, die verschachtelte Bereiche nutzt.](../../../../docs/framework/wpf/controls/media/nested-panels.PNG "nested_panels")  
  
<a name="Panels_custom_panel_elements"></a>   
## <a name="custom-panel-elements"></a>Benutzerdefinierte Panel-Elemente  
 Während [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet eine Reihe von flexible Layoutsteuerelemente, benutzerdefiniertes Layout Verhalten auch werden, durch Überschreiben erzielt können der <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> und <xref:System.Windows.FrameworkElement.MeasureOverride%2A> Methoden. Sie können eine benutzerdefinierte Größe und Position erzielen, indem Sie innerhalb der Methode zum Außerkraftsetzen neues Postionierungsverhalten definieren.  
  
 Auf ähnliche Weise Verhalten von benutzerdefinierten Layouts basierend auf abgeleitete Klassen (z. B. <xref:System.Windows.Controls.Canvas> oder <xref:System.Windows.Controls.Grid>) definiert werden können, durch Überschreiben ihre <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> und <xref:System.Windows.FrameworkElement.MeasureOverride%2A> Methoden.  
  
 Das folgende Markup veranschaulicht das Erstellen eine benutzerdefinierten <xref:System.Windows.Controls.Panel> Element. Diese neue <xref:System.Windows.Controls.Panel>, definiert als `PlotPanel`, unterstützt die Positionierung von untergeordneten Elementen mithilfe von hartcodierten *X -* und *y-*Koordinaten. In diesem Beispiel wird eine <xref:System.Windows.Shapes.Rectangle> Zeichnungsfläche Punkt 50 (nicht dargestellt) Element positioniert ist (*x*), und 50 (*y*).  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 Eine komplexere Implementierung von benutzerdefinierten Panel finden Sie unter [Create a Custom Content-Wrapping Panel Sample (Beispiel für das Erstellen eines Panels zum Umschließen von Inhalt)](http://go.microsoft.com/fwlink/?LinkID=159979).  
  
<a name="Panels_global_localization"></a>   
## <a name="localizationglobalization-support"></a>Unterstützung der Lokalisierung/Globalisierung  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt eine Reihe von Funktionen, die Ihnen beim Erstellen einer lokalisierbaren [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] helfen.  
  
 Systemeigene Unterstützung für alle Bereichselemente der <xref:System.Windows.FrameworkElement.FlowDirection%2A> -Eigenschaft, die verwendet werden können, dynamisch Inhalt basierend auf dem Gebietsschema oder Sprache-Einstellungen eines Benutzers erneut weiterzugeben. Weitere Informationen finden Sie unter <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 Die <xref:System.Windows.Window.SizeToContent%2A> -Eigenschaft bietet einen Mechanismus, die es Anwendungsentwicklern ermöglicht die Anforderungen der voraussichtlich lokalisierten [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Mithilfe der <xref:System.Windows.SizeToContent.WidthAndHeight> Wert dieser Eigenschaft, ein übergeordnetes Element <xref:System.Windows.Window> immer dynamisch Größe an Inhalt und nicht durch künstliche Höhe oder Breite Einschränkungen eingeschränkt ist.  
  
 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, und <xref:System.Windows.Controls.StackPanel> sind alle gute Wahl für lokalisierbare [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. <xref:System.Windows.Controls.Canvas>ist Sie allerdings nicht empfehlenswert, da Inhalte absolut positioniert wird und schwer zu lokalisieren.  
  
 Weitere Informationen zum Erstellen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen mit lokalisierbaren [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)]s finden Sie unter [Übersicht über die Verwendung eines automatischen Layouts](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)  
 [Beispiel für einen WPF-Layoutkatalog](http://go.microsoft.com/fwlink/?LinkID=160054)  
 [Layout](../../../../docs/framework/wpf/advanced/layout.md)  
 [Beispiel für WPF-Steuerelementsammlungen](http://go.microsoft.com/fwlink/?LinkID=160053)  
 [Übersicht über Alignment, Margin und Padding](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)  
 [Erstellen einer benutzerdefinierten Inhalt Wrapping Bereichsbeispiel](http://go.microsoft.com/fwlink/?LinkID=159979)  
 [Übersicht über angefügte Eigenschaften](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)  
 [Übersicht über die Verwendung eines automatischen Layouts](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)
