---
title: "&#220;bersicht &#252;ber Panel-Elemente | Microsoft Docs"
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
  - "Steuerelemente, Bereich"
  - "Panel-Steuerelement [WPF], Informationen über das Panel-Steuerelement"
ms.assetid: f73644af-9941-4611-8754-6d4cef03fc44
caps.latest.revision: 48
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 45
---
# &#220;bersicht &#252;ber Panel-Elemente
<xref:System.Windows.Controls.Panel>\-Elemente sind Komponenten, die das Rendern von Elementen steuern, d. h. ihre Größe und Abmessungen, Ihre Position und die Anordnung des untergeordneten Inhalts.  [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet eine Anzahl vordefinierter <xref:System.Windows.Controls.Panel>\-Elemente sowie die Möglichkeit, benutzerdefinierte <xref:System.Windows.Controls.Panel>\-Elemente zu erstellen.  
  
 Dieses Thema enthält folgende Abschnitte.  
  
-   [Panel\-Klasse](#Panels_view_from_10000_feet)  
  
-   [Allgemeine Member des Panel\-Elements](#Panels_declared_members)  
  
-   [Abgeleitete Panel\-Elemente](#Panels_derived_elements)  
  
-   [Panel\-Elemente für Benutzeroberflächen](#Panels_main_UI_elements)  
  
-   [Geschachtelte Panel\-Elemente](#Panels_nested_panel_elements)  
  
-   [Benutzerdefinierte Panel\-Elemente](#Panels_custom_panel_elements)  
  
-   [Unterstützung der Lokalisierung\/Globalisierung](#Panels_global_localization)  
  
-   [Verwandte Themen](#seeAlsoToggle)  
  
<a name="Panels_view_from_10000_feet"></a>   
## Panel\-Klasse  
 <xref:System.Windows.Controls.Panel> ist die Basisklasse für alle Elemente, die Layoutunterstützung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bereitstellen.  Abgeleitete <xref:System.Windows.Controls.Panel>\-Elemente werden verwendet, um Elemente in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und Code zu positionieren und anzuordnen.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält eine umfassende Suite von abgeleiteten Panel\-Implementierungen, mit denen eine Vielzahl komplexer Layouts möglich sind.  Diese abgeleiteten Klassen machen Eigenschaften und Methoden verfügbar, die die meisten Standard\-[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]\-Szenarien ermöglichen.  Entwickler, die kein Verhalten für das Anordnen untergeordneter Elemente finden können, das ihren Anforderungen entspricht, können neue Layouts erstellen, indem sie die <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>\-Methode und die <xref:System.Windows.FrameworkElement.MeasureOverride%2A>\-Methode überschreiben.  Weitere Informationen über das Verhalten benutzerdefinierter Layouts finden Sie unter [Benutzerdefinierte Panel\-Elemente](#Panels_custom_panel_elements).  
  
<a name="Panels_declared_members"></a>   
## Allgemeine Member von Panel  
 Alle <xref:System.Windows.Controls.Panel>\-Elemente unterstützen die grundlegenden Skalierungs\- und Positionierungseigenschaften, die von <xref:System.Windows.FrameworkElement> definiert werden, einschließlich <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> und <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.  Weitere Informationen über die von <xref:System.Windows.FrameworkElement> definierten Positionierungseigenschaften finden Sie unter [Übersicht über Alignment, Margin und Padding](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md).  
  
 <xref:System.Windows.Controls.Panel> macht zusätzliche Eigenschaften verfügbar, die für das Verständnis und die Verwendung des Layouts besonders wichtig sind.  Die <xref:System.Windows.Controls.Panel.Background%2A>\-Eigenschaft wird verwendet, um den Bereich zwischen den Grenzen eines abgeleiteten Panel\-Elements mit einem <xref:System.Windows.Media.Brush> zu füllen.  <xref:System.Windows.Controls.Panel.Children%2A> stellt die Auflistung untergeordneter Elemente von Elementen dar, aus denen das <xref:System.Windows.Controls.Panel>\-Objekt besteht.  <xref:System.Windows.Controls.Panel.InternalChildren%2A> stellt den Inhalt der <xref:System.Windows.Controls.Panel.Children%2A>\-Auflistung zuzüglich der Member dar, die durch Datenbindung generiert wurden.  Beide bestehen aus einer <xref:System.Windows.Controls.UIElementCollection> untergeordneter Elemente, die im übergeordneten <xref:System.Windows.Controls.Panel> gehostet werden.  
  
 Panel macht auch eine angefügte <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=fullName>\-Eigenschaft verfügbar, die verwendet werden kann, um in einem abgeleiteten <xref:System.Windows.Controls.Panel> Elemente überlagernd anzuordnen.  Die Member der <xref:System.Windows.Controls.Panel.Children%2A>\-Auflistung eines Panel\-Elements, die einen höheren <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=fullName>\-Wert haben, werden vor den Membern mit einem niedrigeren <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=fullName>\-Wert angezeigt.  Dies bietet sich besonders für Panel\-Elemente wie <xref:System.Windows.Controls.Canvas> und <xref:System.Windows.Controls.Grid> an, bei denen untergeordnete Elemente denselben Koordinatenraum gemeinsam nutzen können.  
  
 <xref:System.Windows.Controls.Panel> definiert auch die <xref:System.Windows.Controls.Panel.OnRender%2A>\-Methode, die verwendet werden kann, um das Standard\-Anzeigeverhalten für ein <xref:System.Windows.Controls.Panel>\-Element zu überschreiben.  
  
#### Angefügte Eigenschaften  
 Abgeleitete Panel\-Elemente machen umfassenden Gebrauch von [angefügten Eigenschaften](GTMT).  Eine angefügte Eigenschaft ist eine Sonderform der [Abhängigkeitseigenschaft](GTMT), die nicht den konventionellen [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Eigenschaftenwrapper besitzt.  Angefügte Eigenschaften haben eine besondere Syntax in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], die in mehreren der folgenden Beispiele veranschaulicht wird.  
  
 Ein Zweck einer angefügten Eigenschaft besteht darin, es den untergeordneten Elementen zu ermöglichen, eindeutige Werte einer Eigenschaft zu speichern, die tatsächlich durch ein übergeordnetes Element definiert wird.  Diese Funktion wird z. B. dann angewendet, wenn untergeordnete Elemente übergeordnete Elemente darüber informieren sollen, wie sie in der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] angezeigt werden. Dies ist für das Anwendungslayout sehr nützlich.  Weitere Informationen finden Sie unter [Übersicht über angefügte Eigenschaften](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
<a name="Panels_derived_elements"></a>   
## Abgeleitete Panel\-Elemente  
 Viele Objekte werden von <xref:System.Windows.Controls.Panel> abgeleitet, aber nicht alle sind für die Verwendung als Stammlayoutanbieter ausgelegt.  Es gibt sechs definierte Panel\-Klassen \(<xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel> und <xref:System.Windows.Controls.WrapPanel>\), die speziell für das Erstellen von Anwendungs\-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] vorgesehen sind.  
  
 Jedes Panel\-Element kapselt seine eigene besondere Funktionalität, wie in der folgenden Tabelle gezeigt wird.  
  
|Elementname|Benutzeroberflächen\-Panel?|Beschreibung|  
|-----------------|---------------------------------|------------------|  
|<xref:System.Windows.Controls.Canvas>|Ja|Definiert einen Bereich, in dem Sie untergeordnete Elemente explizit mithilfe von Koordinaten positionieren können, die relativ zum <xref:System.Windows.Controls.Canvas>\-Bereich sind.|  
|<xref:System.Windows.Controls.DockPanel>|Ja|Definiert einen Bereich, in dem Sie untergeordnete Elemente entweder horizontal oder vertikal relativ zueinander anordnen können.|  
|<xref:System.Windows.Controls.Grid>|Ja|Definiert einen flexiblen Rasterbereich, der aus Spalten und Zeilen besteht.  Untergeordnete Elemente eines <xref:System.Windows.Controls.Grid>\-Elements können mit der <xref:System.Windows.FrameworkElement.Margin%2A>\-Eigenschaft genau positioniert werden.|  
|<xref:System.Windows.Controls.StackPanel>|Ja|Ordnet untergeordnete Elemente in einer einzelnen Zeile an, die horizontal oder vertikal ausgerichtet sein kann.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|Nein|Behandelt das Layout von Registerkartenschaltflächen in einem <xref:System.Windows.Controls.TabControl>.|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|Nein|Ordnet Inhalt innerhalb eines <xref:System.Windows.Controls.ToolBar>\-Steuerelements an.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|Nein|<xref:System.Windows.Controls.Primitives.UniformGrid> wird verwendet, um untergeordnete Elemente in einem Raster mit gleich großen Zellen anzuordnen.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|Nein|Stellt eine Basisklasse für Panel\-Elemente bereit, die ihre Auflistung untergeordneter Elemente "virtualisieren" können.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|Ja|Ordnet Inhalt an und virtualisiert Inhalt in einer einzelnen Zeile mit horizontaler oder vertikaler Ausrichtung.|  
|<xref:System.Windows.Controls.WrapPanel>|Ja|<xref:System.Windows.Controls.WrapPanel> positioniert untergeordnete Elemente nacheinander von links nach rechts und bricht den Inhalt am Rand des enthaltenden Felds in die nächste Zeile um.  Je nach dem Wert der <xref:System.Windows.Controls.WrapPanel.Orientation%2A>\-Eigenschaft erfolgt die weitere Anordnung nacheinander von oben nach unten oder von rechts nach links.|  
  
<a name="Panels_main_UI_elements"></a>   
## Panel\-Elemente für Benutzeroberflächen  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stehen sechs Panel\-Klassen zur Verfügung, die für die Unterstützung von [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Szenarien optimiert sind: <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel> und <xref:System.Windows.Controls.WrapPanel>.  Diese Panel\-Elemente sind einfach zu verwenden, vielseitig und können für die meisten Anwendungen ausreichend erweitert werden.  
  
 Jedes abgeleitete <xref:System.Windows.Controls.Panel>\-Element behandelt Einschränkungen für die Größenanpassung unterschiedlich.  Wenn Sie wissen, wie ein <xref:System.Windows.Controls.Panel> Einschränkungen in der horizontalen oder vertikalen Richtung behandelt, kann dies das Layout vorhersagbarer machen.  
  
|****Panel\-Name****|****x\-Dimension****|****y\-Dimension****|  
|-------------------------|--------------------------|--------------------------|  
|<xref:System.Windows.Controls.Canvas>|Eingeschränkt auf Inhalt|Eingeschränkt auf Inhalt|  
|<xref:System.Windows.Controls.DockPanel>|Eingeschränkt|Eingeschränkt|  
|<xref:System.Windows.Controls.StackPanel> \(vertikale Ausrichtung\)|Eingeschränkt|Eingeschränkt auf Inhalt|  
|<xref:System.Windows.Controls.StackPanel> \(horizontale Ausrichtung\)|Eingeschränkt auf Inhalt|Eingeschränkt|  
|<xref:System.Windows.Controls.Grid>|Eingeschränkt|Eingeschränkt, außer in Fällen, in denen <xref:System.Windows.GridUnitType> für Zeilen und Spalten gilt|  
|<xref:System.Windows.Controls.WrapPanel>|Eingeschränkt auf Inhalt|Eingeschränkt auf Inhalt|  
  
 Nachstehend finden Sie ausführlichere Beschreibungen und Verwendungsbeispiele für jedes dieser Elemente.  
  
<a name="Panels_overview_Canvas_subsection"></a>   
### Canvas  
 Das <xref:System.Windows.Controls.Canvas>\-Element ermöglicht die Positionierung des Inhalts entsprechend absoluten *x\-*\-Koordinaten und *y*\-Koordinaten.  Elemente können an einer bestimmten Stelle gezeichnet werden. Wenn Elemente dieselben Koordinaten verwenden, bestimmt die Reihenfolge, in der sie im Markup erscheinen, die Reihenfolge, in der die Elemente gezeichnet werden.  
  
 <xref:System.Windows.Controls.Canvas> ist das <xref:System.Windows.Controls.Panel>\-Element mit der flexibelsten Layoutunterstützung.  Die Eigenschaften Height und Width werden verwendet, um den Bereich des Canvas zu definieren, und den darin enthaltenen Elementen werden absolute Koordinaten zugewiesen, die relativ zum Bereich des übergeordneten <xref:System.Windows.Controls.Canvas> sind.  Mit den vier angehängten Eigenschaften <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=fullName>, <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=fullName>, <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=fullName> und <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=fullName> können Sie die Platzierung von Objekten in einem <xref:System.Windows.Controls.Canvas> genau steuern. Dies ermöglicht es dem Entwickler, Elemente auf dem Bildschirm präzise zu platzieren und anzuordnen.  
  
#### ClipToBounds innerhalb eines Canvas  
 <xref:System.Windows.Controls.Canvas> kann untergeordnete Elemente an jeder beliebigen Position auf dem Bildschirm platzieren, selbst bei Koordinaten, die sich außerhalb der eigenen definierten <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A> befinden.  <xref:System.Windows.Controls.Canvas> wird auch nicht von der Größe seiner untergeordneten Elemente beeinflusst.  Aus diesem Grund ist es für ein untergeordnetes Element möglich, andere Elemente außerhalb des umgebenden Rechtecks des übergeordneten <xref:System.Windows.Controls.Canvas> zu überschreiben.  Das Standardverhalten eines <xref:System.Windows.Controls.Canvas> besteht darin, das Zeichnen untergeordneter Elemente außerhalb des umgebenden Rechtecks des übergeordneten <xref:System.Windows.Controls.Canvas> zu ermöglichen.  Wenn dieses Verhalten unerwünscht ist, kann die <xref:System.Windows.UIElement.ClipToBounds%2A>\-Eigenschaft auf `true` festgelegt werden.  Dadurch wird <xref:System.Windows.Controls.Canvas> auf seine eigene Größe beschnitten.  <xref:System.Windows.Controls.Canvas> ist das einzige Layoutelement, das das Zeichnen untergeordneter Elemente außerhalb seiner Grenzen ermöglicht.  
  
 Dieses Verhalten wird im [Beispiel für den Vergleich von Breiteneigenschaften](http://go.microsoft.com/fwlink/?LinkID=160050) grafisch veranschaulicht.  
  
#### Definieren und Verwenden eines Canvas  
 Ein <xref:System.Windows.Controls.Canvas> kann instanziiert werden, indem man einfach [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oder Code verwendet.  Im folgenden Beispiel wird veranschaulicht, wie <xref:System.Windows.Controls.Canvas> verwendet wird, um Inhalt absolut zu positionieren.  Dieser Code erzeugt drei Quadrate mit einer Seitenlänge von 100 Pixeln.  Das erste Quadrat ist rot, und die obere linke \(*x, y*\)\-Position ist als \(0, 0\) festgelegt.  Das zweite Quadrat ist grün, und die obere linke Position ist \(100, 100\) und befindet sich etwas unterhalb und rechts des ersten Quadrats.  Das dritte Quadrat ist blau, und die obere linke Position ist \(50, 50\). Es umfasst daher den unteren rechten Quadranten des ersten Quadrats und den oberen linken Quadranten des zweiten Quadrats.  Da das dritte Quadrat zuletzt angeordnet wird, scheint es über den beiden anderen Quadraten zu liegen. Die sich überschneidenden Teile nehmen also die Farbe des dritten Quadrats an.  
  
 [!code-csharp[CanvasOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xml[CanvasOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 Die kompilierte Anwendung ergibt eine neue [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], die folgendermaßen aussieht.  
  
 ![Ein typisches Canvas&#45;Element.](../../../../docs/framework/wpf/controls/media/panel-intro-canvas.png "panel\_intro\_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>   
### DockPanel  
 Das <xref:System.Windows.Controls.DockPanel>\-Element verwendet die angefügte <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>\-Eigenschaft, wie in den untergeordneten Inhaltselementen festgelegt ist, um Inhalt an den Rändern eines Containers zu positionieren.  Wenn <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> auf <xref:System.Windows.Controls.Dock> oder <xref:System.Windows.Controls.Dock> festgelegt wird, werden untergeordnete Elemente übereinander oder untereinander positioniert.  Wenn <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> auf <xref:System.Windows.Controls.Dock> oder <xref:System.Windows.Controls.Dock> festgelegt wird, werden untergeordnete Elemente links oder rechts voneinander positioniert.  Die <xref:System.Windows.Controls.DockPanel.LastChildFill%2A>\-Eigenschaft bestimmt die Position des letzten Elements, das als untergeordnetes Element von einem <xref:System.Windows.Controls.DockPanel>\-Element hinzugefügt wird.  
  
 Sie können das <xref:System.Windows.Controls.DockPanel>\-Element verwenden, um eine Gruppe verwandter Steuerelemente zu positionieren, z. B. eine Reihe von Schaltflächen.  Sie können es auch verwenden, um eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mit Panel\-Elementen zu erstellen, die der Benutzeroberfläche in [!INCLUDE[TLA#tla_outlook](../../../../includes/tlasharptla-outlook-md.md)] ähnelt.  
  
#### Größenanpassung an den Inhalt  
 Wenn die <xref:System.Windows.FrameworkElement.Height%2A>\-Eigenschaft und die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft nicht angegeben werden, passt <xref:System.Windows.Controls.DockPanel> seine Größe dem Inhalt an.  Der Inhalt kann je nach der Größe der untergeordneten Elemente größer oder kleiner sein.  Wenn diese Eigenschaften jedoch festgelegt sind und für das nächste angegebene untergeordnete Element kein Platz mehr vorhanden ist, zeigt <xref:System.Windows.Controls.DockPanel> dieses untergeordnete Element und weitere untergeordnete Elemente nicht an und misst die folgenden untergeordneten Elemente nicht.  
  
#### LastChildFill  
 In den Standardeinstellungen füllt das letzte untergeordnete Element eines <xref:System.Windows.Controls.DockPanel>\-Elements den übrigen verfügbaren Platz aus.  Wenn dieses Verhalten unerwünscht ist, legen Sie die <xref:System.Windows.Controls.DockPanel.LastChildFill%2A>\-Eigenschaft auf `false` fest.  
  
#### Definieren und Verwenden eines DockPanel\-Elements  
 Im folgenden Beispiel wird veranschaulicht, wie Bereiche mit einem <xref:System.Windows.Controls.DockPanel>\-Element aufgeteilt werden.  Fünf <xref:System.Windows.Controls.Border>\-Elemente werden als untergeordnete Elemente eines übergeordneten <xref:System.Windows.Controls.DockPanel>\-Elements hinzugefügt.  Jedes Element verwendet eine andere Positionierungseigenschaft eines <xref:System.Windows.Controls.DockPanel>\-Elements, um einen Bereich aufzuteilen.  Das letzte Element "füllt" den verbleibenden verfügbaren Bereich aus.  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 Die kompilierte Anwendung ergibt eine neue [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], die folgendermaßen aussieht.  
  
 ![Ein typisches DockPanel&#45;Szenario.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.png "panel\_intro\_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>   
### Raster  
 Das <xref:System.Windows.Controls.Grid>\-Element führt die Funktionen eines Steuerelements für die absolute Positionierung und eines Tabellendaten\-Steuerelements zusammen.  Mit einem <xref:System.Windows.Controls.Grid> können Sie Elemente problemlos positionieren und formatieren.  <xref:System.Windows.Controls.Grid> ermöglicht es Ihnen, flexible Gruppen von Zeilen und Spalten zu definieren. Dieses Element enthält sogar einen Mechanismus, durch den mehrere <xref:System.Windows.Controls.Grid>\-Elemente die Größeninformationen gemeinsam nutzen können.  
  
#### Was unterscheidet ein Raster von einer Tabelle?  
 <xref:System.Windows.Documents.Table> und <xref:System.Windows.Controls.Grid> haben einige allgemeine Funktionen gemeinsam, sind jedoch beide für unterschiedliche Szenarien geeignet.  Eine <xref:System.Windows.Documents.Table> ist für die Verwendung innerhalb von fortlaufenden Inhalten vorgesehen. \(Weitere Informationen über fortlaufenden Inhalt finden Sie unter [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md).\)  Raster eignen sich am besten für die Verwendung in Formularen \(bzw. außerhalb von fortlaufendem Inhalt\).  In einem <xref:System.Windows.Documents.FlowDocument> unterstützt eine <xref:System.Windows.Documents.Table> verschiedene Verhaltensweisen von fortlaufendem Inhalt wie Paginierung, Tabellenflussrichtung und Inhaltsauswahl, ein <xref:System.Windows.Controls.Grid> dagegen unterstützt dies nicht.  Ein <xref:System.Windows.Controls.Grid> sollte aus verschiedenen Gründen außerhalb eines <xref:System.Windows.Documents.FlowDocument> verwendet werden. Unter anderem fügt ein <xref:System.Windows.Controls.Grid> im Gegensatz zu einer <xref:System.Windows.Documents.Table> Elemente auf Grundlage eines Zeilen\- und Spaltenindexes hinzu.  Das <xref:System.Windows.Controls.Grid>\-Element ermöglicht es, untergeordnete Inhalte überlagernd anzuordnen, sodass mehrere Elemente in einer "Zelle" enthalten sein können. <xref:System.Windows.Documents.Table> unterstützt die Überlagerung nicht.  Die untergeordneten Elemente für ein <xref:System.Windows.Controls.Grid>\-Element können absolut zum Bereich ihrer Zellenbegrenzung positioniert werden.  <xref:System.Windows.Documents.Table> unterstützt dieses Feature nicht.  Ein <xref:System.Windows.Controls.Grid> ist weniger umfangreich als eine <xref:System.Windows.Documents.Table>.  
  
#### Größenanpassungsverhalten von Spalten und Zeilen  
 Für die in einem <xref:System.Windows.Controls.Grid> definierten Spalten und Zeilen können die Vorteile der <xref:System.Windows.GridUnitType>\-Größenanpassung genutzt werden, um den verbleibenden Platz proportional zu verteilen.  Wenn <xref:System.Windows.GridUnitType> als Höhe oder Breite einer Zeile oder Spalte ausgewählt wurde, erhält diese Spalte oder Zeile eine gewichtete Proportion des verbleibenden verfügbaren Platzes.  Im Gegensatz dazu wird bei <xref:System.Windows.GridUnitType> der Platz gleichmäßig auf Grundlage der Größe des Inhalts in einer Spalte oder Zeile verteilt.  Dieser Wert wird als `*` oder `2*` angegeben, wenn Sie [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] verwenden.  Im ersten Fall wird der Zeile oder Spalte der verfügbare Platz genau einmal zugeordnet, im zweiten Fall wird der verfügbare Platz zweimal zugeordnet usw.  Durch Kombinieren dieser Technik für das gleichmäßige Verteilen des Platzes mit dem Wert `Stretch` für <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> ist es möglich, den Layoutplatz nach dem Prozentsatz der Bildschirmfläche aufzuteilen.  <xref:System.Windows.Controls.Grid> ist der einzige Layoutbereich, der den Platz auf diese Weise aufteilen kann.  
  
#### Definieren und Verwenden eines Rasters  
 Im folgenden Beispiel wird gezeigt, wie Sie eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] erstellen, die dem im Startmenü von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] verwendeten Dialogfeld Ausführen ähnelt.  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 Die kompilierte Anwendung ergibt eine neue [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], die folgendermaßen aussieht.  
  
 ![Ein typisches Rasterelement.](../../../../docs/framework/wpf/controls/media/avalon-run-dialog.png "avalon\_run\_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>   
### StackPanel  
 Ein <xref:System.Windows.Controls.StackPanel>\-Element ermöglicht es Ihnen, Elemente in einer zugewiesenen Richtung zu "stapeln".  Standardmäßig ist die Stapelrichtung vertikal.  Sie können den fortlaufenden Inhalt mithilfe der <xref:System.Windows.Controls.StackPanel.Orientation%2A>\-Eigenschaft steuern.  
  
#### StackPanel im Vergleich zuDockPanel  
 Obwohl <xref:System.Windows.Controls.DockPanel> ebenfalls zum Stapeln von untergeordneten Elementen verwendet werden kann, führen <xref:System.Windows.Controls.DockPanel> und <xref:System.Windows.Controls.StackPanel> in manchen Szenarien nicht immer zu gleichen Ergebnissen.  Beispielsweise kann in einem <xref:System.Windows.Controls.DockPanel>\-Element die Reihenfolge der untergeordneten Elemente ihre Größe beeinflussen. In einem <xref:System.Windows.Controls.StackPanel>\-Element ist das jedoch nicht der Fall.  Dies liegt daran, dass das <xref:System.Windows.Controls.StackPanel>\-Element in Stapelrichtung bei <xref:System.Double.PositiveInfinity> misst, wohingegen das <xref:System.Windows.Controls.DockPanel>\-Element nur die verfügbare Größe misst.  
  
 Im folgenden Beispiel wird dieser wichtige Unterschied veranschaulicht.  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 Dieses Bild zeigt den Unterschied im Renderingverhalten.  
  
 ![Screenshot: StackPanel im Vergleich zu DockPanel&#45;Screenshot](../../../../docs/framework/wpf/controls/media/layout-smiley-stackpanel.png "layout\_smiley\_stackpanel")  
  
#### Definieren und Verwenden eines StackPanel\-Elements  
 Im folgenden Beispiel wird veranschaulicht, wie mit einem <xref:System.Windows.Controls.StackPanel>\-Element eine Reihe vertikal positionierter Schaltflächen erstellt wird.  Legen Sie die <xref:System.Windows.Controls.StackPanel.Orientation%2A>\-Eigenschaft auf <xref:System.Windows.Controls.Orientation> fest, um eine horizontale Positionierung zu erzielen.  
  
 [!code-csharp[StackPanel_ovw2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 Die kompilierte Anwendung ergibt eine neue [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], die folgendermaßen aussieht.  
  
 ![Ein typisches StackPanel&#45;Element.](../../../../docs/framework/wpf/controls/media/panel-intro-stackpanel.png "panel\_intro\_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>   
#### VirtualizingStackPanel  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt außerdem eine Variante des <xref:System.Windows.Controls.StackPanel>\-Elements bereit, das datengebundenen untergeordneten Inhalt automatisch "virtualisiert".  In diesem Zusammenhang bezeichnet "virtualisieren" eine Vorgehensweise, bei der eine Teilmenge von Elementen aus einer größeren Anzahl von Datenelementen generiert wird, wobei berücksichtigt wird, welche Elemente auf dem Bildschirm angezeigt werden.  Das Generieren einer großen Anzahl von Benutzeroberflächenelementen nimmt sehr viel Arbeitsspeicher und Prozessorleistung in Anspruch, auch wenn jeweils nur einige der Elemente auf dem Bildschirm angezeigt werden.  <xref:System.Windows.Controls.VirtualizingStackPanel> \(mithilfe der Funktionen von <xref:System.Windows.Controls.VirtualizingPanel>\) berechnet die sichtbaren Elemente und erstellt dann zusammen mit dem <xref:System.Windows.Controls.ItemContainerGenerator> aus einem <xref:System.Windows.Controls.ItemsControl> \(z. B. einem <xref:System.Windows.Controls.ListBox> oder einer <xref:System.Windows.Controls.ListView>\) nur die Elemente für die sichtbaren Elemente  
  
 Das <xref:System.Windows.Controls.VirtualizingStackPanel>\-Element wird automatisch als Elementhost für Steuerelemente wie das <xref:System.Windows.Controls.ListBox> festgelegt.  Wenn eine datengebundene Auflistung gehostet wird, wird der Inhalt automatisch virtualisiert, solange der Inhalt sich innerhalb der Grenzen eines <xref:System.Windows.Controls.ScrollViewer>\-Elements befindet.  Dadurch wird die Leistung beim Hosten vieler untergeordneter Elemente erheblich verbessert.  
  
 Das folgende Markup veranschaulicht, wie ein <xref:System.Windows.Controls.VirtualizingStackPanel>\-Element als Elementhost verwendet wird.  Die angehängte <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=fullName> [\-Eigenschaft](GTMT) muss auf `true` \(Standard\) festgelegt werden, damit die Virtualisierung ausgeführt wird.  
  
 [!code-xml[VirtualizingStackPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>   
### WrapPanel  
 <xref:System.Windows.Controls.WrapPanel> wird verwendet, um untergeordnete Elemente nacheinander von links nach rechts zu positionieren, wobei der Inhalt in die nächste Zeile umbrochen wird, sobald der Rand des übergeordneten Containers erreicht wird.  Der Inhalt kann horizontal oder vertikal ausgerichtet werden.  <xref:System.Windows.Controls.WrapPanel> eignet sich für einfache Szenarien mit fließender [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  WrapPanel kann auch verwendet werden, um eine einheitliche Größe auf alle untergeordneten Elemente anzuwenden.  
  
 Das folgende Beispiel veranschaulicht, wie ein <xref:System.Windows.Controls.WrapPanel>\-Element erstellt wird, um <xref:System.Windows.Controls.Button>\-Steuerelemente anzuzeigen, die umbrochen werden, wenn sie den Rand des Containers erreichen.  
  
 [!code-cpp[WrapPanel_Intro#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xml[WrapPanel_Intro#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 Die kompilierte Anwendung ergibt eine neue [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], die folgendermaßen aussieht.  
  
 ![Ein typisches WrapPanel&#45;Element.](../../../../docs/framework/wpf/controls/media/wrappanel-element.png "WrapPanel\_Element")  
  
<a name="Panels_nested_panel_elements"></a>   
## Geschachtelte Panel\-Elemente  
 <xref:System.Windows.Controls.Panel>\-Elemente können ineinander geschachtelt werden, um komplexe Layouts zu erzeugen.  Dies kann sich in Situationen als sehr nützlich erweisen, in denen ein <xref:System.Windows.Controls.Panel>\-Element für einen Teil der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] geeignet ist, aber möglicherweise nicht die Anforderungen eines anderen Teils der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] erfüllt.  
  
 Es gibt praktisch keine Begrenzung für die Anzahl der Schachtelungen, die Ihre Anwendung unterstützen kann. Es empfiehlt sich jedoch, in Ihrer Anwendung nur die Panel\-Elemente zu verwenden, die für das gewünschte Layout tatsächlich notwendig sind.  In vielen Fällen kann ein <xref:System.Windows.Controls.Grid>\-Element statt geschachtelter Panel\-Elemente verwendet werden, da es als Layoutcontainer flexibel ist.  Dies kann die Leistung der Anwendung erhöhen, da keine unnötigen Elemente in der Struktur verwendet werden.  
  
 Das folgende Beispiel veranschaulicht, wie eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] erstellt wird, die geschachtelte <xref:System.Windows.Controls.Panel>\-Elemente nutzt, um ein bestimmtes Layout zu erzielen.  In diesem speziellen Fall wird ein <xref:System.Windows.Controls.DockPanel>\-Element verwendet, um die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Struktur bereitzustellen. Geschachtelte <xref:System.Windows.Controls.StackPanel>\-Elemente, ein <xref:System.Windows.Controls.Grid> und ein <xref:System.Windows.Controls.Canvas> werden verwendet, um untergeordnete Elemente im übergeordneten <xref:System.Windows.Controls.DockPanel>\-Element genau zu positionieren.  
  
 [!code-csharp[Nested_Panels#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 Die kompilierte Anwendung ergibt eine neue [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], die folgendermaßen aussieht.  
  
 ![Eine UI, die verschachtelte Bereiche nutzt.](../../../../docs/framework/wpf/controls/media/nested-panels.png "nested\_panels")  
  
<a name="Panels_custom_panel_elements"></a>   
## Benutzerdefinierte Panel\-Elemente  
 Während [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein Array von flexiblen Layout\-Steuerelementen bereitstellt, kann benutzerdefiniertes Layoutverhalten auch erzielt werden, indem die <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>\-Methode und die <xref:System.Windows.FrameworkElement.MeasureOverride%2A>\-Methode überschrieben werden.  Benutzerdefinierte Größenanpassung und Positionierung kann auch ermöglicht werden, indem neue Positionierungsverhalten innerhalb dieser Überschreibungsmethoden definiert werden.  
  
 Auf ähnliche Weise können benutzerdefinierte Layoutverhalten, die auf abgeleiteten Klassen basieren \(z. B. <xref:System.Windows.Controls.Canvas> oder <xref:System.Windows.Controls.Grid>\) definiert werden, indem die zugehörige <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>\-Methode und die <xref:System.Windows.FrameworkElement.MeasureOverride%2A>\-Methode überschrieben werden.  
  
 Das folgende Markup veranschaulicht, wie ein benutzerdefiniertes <xref:System.Windows.Controls.Panel>\-Element erstellt wird.  Dieses neue <xref:System.Windows.Controls.Panel>\-Element, definiert als `PlotPanel`, unterstützt die Positionierung von untergeordneten Elementen durch Verwendung von hartcodierten *x\-* und *y\-*Koordinaten.  In diesem Beispiel wird ein <xref:System.Windows.Shapes.Rectangle>\-Element \(nicht angezeigt\) am Zeichnungspunkt 50 \(*x*\) und 50 \(*y*\) positioniert.  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 Eine komplexere Implementierung von benutzerdefinierten Panel\-Elementen finden Sie unter [Erstellen eines Beispiels für einen Bereich mit benutzerdefiniertem Inhaltsumbruch](http://go.microsoft.com/fwlink/?LinkID=159979).  
  
<a name="Panels_global_localization"></a>   
## Unterstützung der Lokalisierung\/Globalisierung  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt eine Anzahl von Features, die Ihnen bei der Erstellung einer lokalisierbaren [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] helfen.  
  
 Alle Panel\-Elemente unterstützen direkt die <xref:System.Windows.FrameworkElement.FlowDirection%2A>\-Eigenschaft, mit der Inhalt dynamisch neu aufgebaut werden kann, der auf dem Gebietsschema oder den Spracheinstellungen eines Benutzers basiert.  Weitere Informationen finden Sie unter <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 Die <xref:System.Windows.Window.SizeToContent%2A>\-Eigenschaft stellt einen Mechanismus bereit, der es Anwendungsentwicklern ermöglicht, die Anforderungen lokalisierter [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] einzuschätzen.  Mithilfe des <xref:System.Windows.SizeToContent>\-Werts dieser Eigenschaft wird die Größe für ein übergeordnetes <xref:System.Windows.Window> immer dynamisch an den Inhalt angepasst und ist nicht durch künstliche Höhen\- oder Breitenangaben eingeschränkt.  
  
 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid> und <xref:System.Windows.Controls.StackPanel> sind geeignete Elemente für eine lokalisierbare [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  <xref:System.Windows.Controls.Canvas> ist nicht geeignet, da der Inhalt absolut positioniert wird und damit die Lokalisierung schwierig ist.  
  
 Weitere Informationen über das Erstellen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen mit lokalisierbarer [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)] finden Sie unter [Übersicht über die Verwendung eines automatischen Layouts](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md).  
  
## Siehe auch  
 [Exemplarische Vorgehensweise: Erste Schritte mit WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)   
 [Beispiel für einen WPF\-Layoutkatalog](http://go.microsoft.com/fwlink/?LinkID=160054)   
 [Layout](../../../../docs/framework/wpf/advanced/layout.md)   
 [Beispiel für WPF\-Steuerelementsammlungen](http://go.microsoft.com/fwlink/?LinkID=160053)   
 [Übersicht über Alignment, Margin und Padding](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)   
 [Erstellen eines Beispiels für einen Bereich mit benutzerdefiniertem Inhaltsumbruch](http://go.microsoft.com/fwlink/?LinkID=159979)   
 [Übersicht über angefügte Eigenschaften](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)   
 [Übersicht über die Verwendung eines automatischen Layouts](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)   
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)