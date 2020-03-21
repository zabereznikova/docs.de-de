---
title: Übersicht über das Rendern von Grafiken
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rendering
- rendering graphics [WPF]
ms.assetid: 6dec9657-4d8c-4e46-8c54-40fb80008265
ms.openlocfilehash: 9d58aa973f7de6c073611e13f2889913ff26dd55
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111919"
---
# <a name="wpf-graphics-rendering-overview"></a>Übersicht über das WPF-Grafikrendering
Das Thema bietet einen Überblick über die visuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Schicht. Es konzentriert sich auf <xref:System.Windows.Media.Visual> die Rolle der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Klasse für das Rendern von Unterstützung im Modell.  

<a name="role_of_visual_object"></a>
## <a name="role-of-the-visual-object"></a>Rolle des visuellen Objekts  
 Die <xref:System.Windows.Media.Visual> Klasse ist die grundlegende Abstraktion, von der jedes <xref:System.Windows.FrameworkElement> Objekt ableitet. Sie dient auch als Einstiegspunkt zum Schreiben neuer Steuerelemente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und kann in vielerlei Hinsicht als Fensterhandle (HWND) im Win32-Anwendungsmodell betrachtet werden.  
  
 Das <xref:System.Windows.Media.Visual> Objekt ist [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein Kernobjekt, dessen primäre Rolle darin besteht, Renderingunterstützung bereitzustellen. Benutzeroberflächensteuerelemente, <xref:System.Windows.Controls.Button> z. B. <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Media.Visual> und , leiten sich von der Klasse ab und verwenden sie zum Beibehalten ihrer Renderingdaten. Das <xref:System.Windows.Media.Visual> Objekt bietet Unterstützung für:  
  
- Ausgabeanzeige: Rendern des persistenten, serialisierten Zeichnungsinhalts eines visuellen Objekts.  
  
- Transformationen: Ausführen von Transformationen auf einem visuellen Objekt.  
  
- Clipping: Bereitstellen der Clippingbereichsunterstützung für ein visuelles Objekt.  
  
- Treffertests: Bestimmen, ob eine Koordinate oder eine Geometrie innerhalb der Grenzen eines visuellen Objekts enthalten ist.  
  
- Berechnungen des Begrenzungsrahmens: Bestimmen des umschließenden Rechtecks eines visuellen Objekts.  
  
 Das <xref:System.Windows.Media.Visual> Objekt enthält jedoch keine Unterstützung für nicht-rendering-Features, z. B.:  
  
- Behandlung von Ereignissen  
  
- Layout  
  
- Stile  
  
- Datenbindung  
  
- Globalisierung  
  
 <xref:System.Windows.Media.Visual>wird als öffentliche abstrakte Klasse verfügbar gemacht, von der untergeordnete Klassen abgeleitet werden müssen. Die folgende Abbildung zeigt die Hierarchie der visuellen Objekte, die in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügbar gemacht werden.  
  
 ![Diagramm der vom Visual-Objekt abgeleiteten Klassen](./media/wpf-graphics-rendering-overview/classes-derived-visual-object.png)
  
### <a name="drawingvisual-class"></a>DrawingVisual-Klasse  
 Die <xref:System.Windows.Media.DrawingVisual> ist eine einfache Zeichnungsklasse, die zum Rendern von Formen, Bildern oder Text verwendet wird. Diese Klasse wird als einfach angesehen, da sie keine Layout- oder Ereignisbehandlung bereitstellt, was die Laufzeitleistung verbessert. Aus diesem Grund eignen sich Zeichnungen für Hintergründe und ClipArt. Der <xref:System.Windows.Media.DrawingVisual> kann verwendet werden, um ein benutzerdefiniertes visuelles Objekt zu erstellen. Weitere Informationen finden Sie unter [Verwenden von DrawingVisual-Objekten](using-drawingvisual-objects.md).  
  
### <a name="viewport3dvisual-class"></a>Viewport3DVisual-Klasse  
 Der <xref:System.Windows.Media.Media3D.Viewport3DVisual> stellt eine Brücke <xref:System.Windows.Media.Visual> <xref:System.Windows.Media.Media3D.Visual3D> zwischen 2D und Objekten bereit. Die <xref:System.Windows.Media.Media3D.Visual3D> Klasse ist die Basisklasse für alle visuellen 3D-Elemente. Die <xref:System.Windows.Media.Media3D.Viewport3DVisual> erfordert, dass <xref:System.Windows.Media.Media3D.Viewport3DVisual.Camera%2A> Sie <xref:System.Windows.Media.Media3D.Viewport3DVisual.Viewport%2A> einen Wert und einen Wert definieren. Die Kamera ermöglicht die Anzeige der Szene. Der Anzeigebereich legt fest, wo die Projektion auf der 2D-Fläche zuordnet. Weitere Informationen zu 3D in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]finden Sie unter [3D Graphics Overview](3-d-graphics-overview.md).  
  
### <a name="containervisual-class"></a>ContainerVisual-Klasse  
 Die <xref:System.Windows.Media.ContainerVisual> Klasse wird als Container für <xref:System.Windows.Media.Visual> eine Auflistung von Objekten verwendet. Die <xref:System.Windows.Media.DrawingVisual> Klasse leitet sich <xref:System.Windows.Media.ContainerVisual> von der Klasse ab, sodass sie eine Auflistung visueller Objekte enthalten kann.  
  
### <a name="drawing-content-in-visual-objects"></a>Zeichnungsinhalt in visuellen Objekten  
 Ein <xref:System.Windows.Media.Visual> Objekt speichert seine Renderdaten als **Vektorgrafikanweisungsliste**. Jedes Element in der Anweisungsliste stellt einen Satz von Grafikdaten einer niedrigeren Ebene und dazugehörige Ressourcen in einem serialisierten Format dar. Es gibt vier verschiedene Typen von Renderingdaten, die Zeichnungsinhalt enthalten können.  
  
|Zeichnungsinhaltstyp|Beschreibung|  
|--------------------------|-----------------|  
|Vektorgrafik|Stellt Vektorgrafikdaten sowie <xref:System.Windows.Media.Brush> alle <xref:System.Windows.Media.Pen> zugehörigen Informationen und Informationen dar.|  
|Image|Stellt ein Bild innerhalb eines <xref:System.Windows.Rect>Bereichs dar, der durch eine definiert ist.|  
|Glyphe|Stellt eine Zeichnung dar, die eine <xref:System.Windows.Media.GlyphRun>rendert, bei der es sich um eine Folge von Glyphen aus einer angegebenen Schriftartressource handelt. So wird Text dargestellt.|  
|Video|Stellt eine Zeichnung dar, die Video rendert.|  
  
 Mit <xref:System.Windows.Media.DrawingContext> der können Sie <xref:System.Windows.Media.Visual> einen mit visuellen Inhalten füllen. Wenn Sie <xref:System.Windows.Media.DrawingContext> die Zeichnungsbefehle eines Objekts verwenden, speichern Sie tatsächlich einen Satz von Renderdaten, die später vom Grafiksystem verwendet werden. Sie werden nicht in Echtzeit auf den Bildschirm gezeichnet.  
  
 Wenn Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein Steuerelement erstellen, z. B. ein <xref:System.Windows.Controls.Button>, generiert das Steuerelement implizit Renderdaten für das Zeichnen selbst. Wenn Sie z. B. die <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft des <xref:System.Windows.Controls.Button> bewirkt, dass das Steuerelement eine Renderingdarstellung einer Glyphe speichert.  
  
 A <xref:System.Windows.Media.Visual> beschreibt seinen Inhalt <xref:System.Windows.Media.Drawing> als ein <xref:System.Windows.Media.DrawingGroup>oder mehrere Objekte, die in einer enthalten sind. A <xref:System.Windows.Media.DrawingGroup> beschreibt auch Deckkraftmasken, Transformationen, Bitmapeffekte und andere Vorgänge, die auf den Inhalt angewendet werden. <xref:System.Windows.Media.DrawingGroup>Vorgänge werden in der folgenden Reihenfolge angewendet, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>wenn <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A> <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>Inhalt gerendert <xref:System.Windows.Media.DrawingGroup.Transform%2A>wird: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, , , und dann .  
  
 Die folgende Abbildung zeigt <xref:System.Windows.Media.DrawingGroup> die Reihenfolge, in der Vorgänge während der Rendersequenz angewendet werden.  
  
 ![DrawingGroup-Reihenfolge der Vorgänge](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Reihenfolge der DrawingGroup-Vorgänge  
  
 Weitere Informationen finden Sie unter [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md).  
  
#### <a name="drawing-content-at-the-visual-layer"></a>Zeichnungsinhalt auf Ebene des visuellen Objekts  
 Sie instanziieren nie <xref:System.Windows.Media.DrawingContext>direkt eine ; Sie können jedoch einen Zeichnungskontext aus bestimmten <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>Methoden abrufen, z. B. und . Im folgenden Beispiel <xref:System.Windows.Media.DrawingContext> wird <xref:System.Windows.Media.DrawingVisual> ein aus einem abgerufen und zum Zeichnen eines Rechtecks verwendet.  
  
 [!code-csharp[drawingvisualsample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[drawingvisualsample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
#### <a name="enumerating-drawing-content-at-the-visual-layer"></a>Auflisten des Zeichnungsinhalts auf der Ebene eines visuellen Objekts  
 Zusätzlich zu ihren anderen <xref:System.Windows.Media.Drawing> Verwendungen stellen Objekte auch ein Objektmodell <xref:System.Windows.Media.Visual>zum Aufzählen des Inhalts einer bereit.  
  
> [!NOTE]
> Wenn Sie den Inhalt des visuellen Elements auflisten, werden <xref:System.Windows.Media.Drawing> Objekte abgerufen, und nicht die zugrunde liegende Darstellung der Renderdaten als Vektorgrafikanweisungsliste.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> wird die <xref:System.Windows.Media.DrawingGroup> Methode <xref:System.Windows.Media.Visual> verwendet, um den Wert von a abzurufen und aufzuzählen.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
<a name="how_visual_objects_are_used_to_build_controls"></a>
## <a name="how-visual-objects-are-used-to-build-controls"></a>Verwenden von visuellen Objekten zum Erstellen von Steuerelementen  
 Viele der Objekte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bestehen aus anderen visuellen Objekten, d.h., sie können unterschiedliche Hierarchien von untergeordneten Objekten enthalten. Viele Benutzeroberflächenelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], z.B. Steuerelemente, bestehen aus mehreren visuellen Objekten, die unterschiedliche Typen von Renderingelementen darstellen. <xref:System.Windows.Controls.Button> Das Steuerelement kann z. B. eine <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>Reihe <xref:System.Windows.Controls.ContentPresenter>anderer <xref:System.Windows.Controls.TextBlock>Objekte enthalten, einschließlich , und .  
  
 Der folgende Code <xref:System.Windows.Controls.Button> zeigt ein in Markup definiertes Steuerelement.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet1)]  
  
 Wenn Sie die visuellen Objekte aufzählen würden, aus denen das Standardsteuerelement <xref:System.Windows.Controls.Button> besteht, finden Sie die hierarchien der visuellen Objekte, die unten dargestellt sind:  
  
 ![Diagramm der visuellen Strukturhierarchie](./media/wpf-graphics-rendering-overview/visual-object-diagram.gif)
  
 Das <xref:System.Windows.Controls.Button> Steuerelement <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> enthält ein Element, das <xref:System.Windows.Controls.ContentPresenter> wiederum ein Element enthält. Das <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> Element ist für das Zeichnen eines <xref:System.Windows.Controls.Button>Rahmens und eines Hintergrunds für die verantwortlich. Das <xref:System.Windows.Controls.ContentPresenter> Element ist für die <xref:System.Windows.Controls.Button>Anzeige des Inhalts der verantwortlich. In diesem Fall enthält das <xref:System.Windows.Controls.ContentPresenter> Element, da <xref:System.Windows.Controls.TextBlock> Sie Text anzeigen, ein Element. Die Tatsache, <xref:System.Windows.Controls.Button> dass <xref:System.Windows.Controls.ContentPresenter> das Steuerelement ein Mittel verwendet, mit dem <xref:System.Windows.Controls.Image> der Inhalt durch <xref:System.Windows.Media.EllipseGeometry>andere Elemente dargestellt werden kann, z. B. eine oder eine Geometrie, z. B. eine .  
  
### <a name="control-templates"></a>Steuerelementvorlagen  
 Der Schlüssel zur Erweiterung eines Steuerelements in <xref:System.Windows.Controls.ControlTemplate>eine Hierarchie von Steuerelementen ist die . Eine Steuerelementvorlage gibt die visuelle Standardhierarchie für ein Steuerelement an. Wenn Sie explizit auf ein Steuerelement verweisen, verweisen Sie implizit auf dessen visuelle Hierarchie. Sie können die Standardwerte für eine Steuerelementvorlage überschreiben, um eine angepasste visuelle Darstellung für ein Steuerelement zu erstellen. Sie können z. B. den <xref:System.Windows.Controls.Button> Hintergrundfarbwert des Steuerelements so ändern, dass es einen linearen Farbverlaufswert anstelle eines Volltonfarbwerts verwendet. Weitere Informationen finden Sie unter [Button-Stile und Vorlagen](../controls/button-styles-and-templates.md).  
  
 Ein Benutzeroberflächenelement, z. B. ein <xref:System.Windows.Controls.Button> Steuerelement, enthält mehrere Vektorgrafikanweisungslisten, die die gesamte Renderingdefinition eines Steuerelements beschreiben. Der folgende Code <xref:System.Windows.Controls.Button> zeigt ein in Markup definiertes Steuerelement.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet2)]  
  
 Wenn Sie die visuellen Objekte und Vektorgrafik-Anweisungslisten <xref:System.Windows.Controls.Button> auflisten würden, aus denen das Steuerelement besteht, finden Sie die unten dargestellte Hierarchie der Objekte:  
  
 ![Diagramm der visuellen Struktur und des Renderings von Daten](./media/wpf-graphics-rendering-overview/visual-tree-rendering-data.png)  
  
 Das <xref:System.Windows.Controls.Button> Steuerelement <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> enthält ein Element, das <xref:System.Windows.Controls.ContentPresenter> wiederum ein Element enthält. Das <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> Element ist für das Zeichnen aller diskreten grafikelemente verantwortlich, aus denen sich der Rahmen und der Hintergrund einer Schaltfläche zusammenfinden. Das <xref:System.Windows.Controls.ContentPresenter> Element ist für die <xref:System.Windows.Controls.Button>Anzeige des Inhalts der verantwortlich. Da Sie in diesem Fall ein <xref:System.Windows.Controls.ContentPresenter> Bild anzeigen, enthält das Element ein <xref:System.Windows.Controls.Image> Element.  
  
 Es gibt mehrere Dinge im Zusammenhang mit der Hierarchie von visuellen Objekten und Anweisungslisten für Vektorgrafiken zu beachten:  
  
- Die Reihenfolge in der Hierarchie stellt die Renderingreihenfolge der Zeichnungsinformationen dar. Aus dem visuellen Stammelement werden untergeordnete Elemente von links nach rechts und von oben nach unten durchlaufen. Wenn ein Element über visuelle untergeordnete Elemente verfügt, werden diese vor den gleichgeordneten Elementen des Elements durchlaufen.  
  
- Nicht-Blattknotenelemente in der Hierarchie, z. <xref:System.Windows.Controls.ContentPresenter>B. , werden verwendet, um untergeordnete Elemente zu enthalten – sie enthalten keine Anweisungslisten.  
  
- Wenn ein visuelles Element eine Anweisungsliste für Vektorgrafiken und visuelle untergeordnete Elemente enthält, wird die Anweisungsliste im übergeordneten visuellen Element vor Zeichnungen in einem der untergeordneten visuellen Objekte gerendert.  
  
- Die Elemente in der Anweisungsliste für Vektorgrafiken werden von links nach rechts gerendert.  
  
<a name="visual_tree"></a>
## <a name="visual-tree"></a>Visuelle Struktur  
 Die visuelle Struktur enthält alle visuellen Elemente, die in der Benutzeroberfläche einer Anwendung verwendet werden. Da ein visuelles Element persistent gespeicherte Zeichnungsinformationen enthält, können Sie sich die visuelle Struktur als Szenengraph vorstellen, der alle Renderinginformationen enthält, die erforderlich sind, um die Ausgabe auf dem Anzeigegerät zu erstellen. Diese Struktur ist die Ansammlung aller visuellen Elemente, die direkt von der Anwendung im Code oder im Markup erstellt werden. Die visuelle Struktur enthält auch alle visuellen Elemente, die von der Vorlagenerweiterung der Elemente, wie z.B. Steuerelemente und Datenobjekte, erstellt werden.  
  
 Der folgende Code <xref:System.Windows.Controls.StackPanel> zeigt ein in Markup definiertes Element.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet3)]  
  
 Wenn Sie die visuellen Objekte aufzählen <xref:System.Windows.Controls.StackPanel> würden, aus denen das Element im Markupbeispiel besteht, finden Sie die hierarchien der visuellen Objekte, die unten dargestellt werden:  
  
 ![Diagramm der visuellen Strukturhierarchie](./media/wpf-graphics-rendering-overview/visual-tree-hierarchy.gif)  
  
### <a name="rendering-order"></a>Renderingreihenfolge  
 Die visuelle Struktur bestimmt die Renderingreihenfolge der visuellen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und Zeichnungsobjekte. Die Reihenfolge des Durchlaufs beginnt mit dem visuellen Stammelement, das der oberste Knoten in der visuellen Struktur ist. Die untergeordnete Elemente des visuellen Stammelements werden von links nach rechts durchlaufen. Wenn ein visuelles Objekt über untergeordnete Elemente verfügt, werden seine untergeordneten Elemente vor den gleichgeordneten visuellen Elementen durchlaufen. Dies bedeutet, dass der Inhalt eines untergeordneten visuellen Objekts vor dem Inhalt des visuellen Objekts selbst gerendert wird.  
  
 ![Diagramm der visuellen Struktur-Rendering-Reihenfolge](./media/wpf-graphics-rendering-overview/visual-tree-rendering-order.gif)
  
### <a name="root-visual"></a>Visuelles Stammobjekt  
 Das **visuelle Stammobjekt** ist das oberste Element in der Hierarchie einer visuellen Struktur. In den meisten Anwendungen ist die Basisklasse des Root Visualentweder oder <xref:System.Windows.Window> . <xref:System.Windows.Navigation.NavigationWindow> Wenn Sie jedoch visuelle Objekte in einer Win32-Anwendung hosten, ist das visuelle Stammobjekt das oberste visuelle Objekt, das Sie im Win32-Fenster hosten. Weitere Informationen finden Sie unter [Tutorial: Hosten von visuellen Objekten in einer Win32-Anwendung](tutorial-hosting-visual-objects-in-a-win32-application.md).  
  
### <a name="relationship-to-the-logical-tree"></a>Beziehung zur logischen Struktur  
 Die logische Struktur in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt die Elemente einer Anwendung zur Laufzeit dar. Obwohl Sie die Struktur nicht direkt bearbeiten, ist diese Ansicht der Anwendung nützlich, um die Vererbung von Eigenschaften und das Ereignisrouting nachzuvollziehen. Im Gegensatz zur visuellen Struktur kann die logische Struktur <xref:System.Windows.Documents.ListItem>nicht-visuelle Datenobjekte darstellen, z. B. . In vielen Fällen ist die logische Struktur eng an die Markupdefinitionen einer Anwendung angelehnt. Der folgende Code <xref:System.Windows.Controls.DockPanel> zeigt ein in Markup definiertes Element.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet5)]  
  
 Wenn Sie die logischen Objekte aufzählen <xref:System.Windows.Controls.DockPanel> würden, aus denen das Element im Markupbeispiel besteht, finden Sie die hierarchieder logischer Objekte, die unten dargestellt sind:  
  
 ![Strukturdiagramm](./media/tree1-wcp.gif "Tree1_wcp")  
Diagramm der logischen Struktur  
  
 Die visuelle Struktur und die logische Struktur werden mit dem aktuellen Satz von Anwendungselementen synchronisiert und spiegeln dabei alle Hinzufügungen, Löschungen oder Änderungen von Elementen wider. Die Strukturen liefern jedoch verschiedene Ansichten der Anwendung. Im Gegensatz zur visuellen Struktur erweitert die <xref:System.Windows.Controls.ContentPresenter> logische Struktur das Element eines Steuerelements nicht. Dies bedeutet, dass keine direkte 1:1-Entsprechung zwischen einer logischen Struktur und einer visuellen Struktur für den gleichen Satz von Objekten vorhanden ist. Das Aufrufen der <xref:System.Windows.LogicalTreeHelper.GetChildren%2A> **LogicalTreeHelper-Objektmethode** und der Methode des **VisualTreeHelper-Objekts** <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A> mithilfe desselben Elements wie eines Parameters führt zu unterschiedlichen Ergebnissen.  
  
 Weitere Informationen zu der logischen Struktur finden Sie unter [Strukturen in WPF](../advanced/trees-in-wpf.md).  
  
### <a name="viewing-the-visual-tree-with-xamlpad"></a>Anzeigen der visuellen Struktur mit XamlPad  
 Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Tool XamlPad bietet eine Option zum Anzeigen und Erkunden der visuellen Struktur, die dem aktuell definierten XAML-Inhalt entspricht. Klicken Sie auf die Schaltfläche **Visuelle Struktur anzeigen** der Menüleiste, um die visuelle Struktur anzuzeigen. Im Folgenden wird die Erweiterung von XAML-Inhalten in visuelle Baumknoten im **Visual Tree Explorer-Bedienfeld** von XamlPad veranschaulicht:  
  
 ![Visueller Struktur-Explorer-Bereich in XamlPad](./media/wpf-graphics-rendering-overview/visual-tree-explorer.png)  

 Beachten Sie, <xref:System.Windows.Controls.TextBox>wie <xref:System.Windows.Controls.Button> die <xref:System.Windows.Controls.Label>, und Steuerelemente jeweils eine separate visuelle Objekthierarchie im **Visual Tree Explorer-Bedienfeld** von XamlPad anzeigen. Dies [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] liegt daran, dass Steuerelemente eine <xref:System.Windows.Controls.ControlTemplate> haben, die die visuelle Struktur dieses Steuerelements enthält. Wenn Sie explizit auf ein Steuerelement verweisen, verweisen Sie implizit auf dessen visuelle Hierarchie.  
  
### <a name="profiling-visual-performance"></a>Erstellung von visuellen Leistungsprofilen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt eine Suite von Leistungsprofilerstellungstools bereit, mit deren Hilfe Sie das Laufzeitverhalten der Anwendung analysieren und die Typen der anwendbaren Leistungsoptimierungen bestimmen können. Das Visual Profiler-Tool bietet eine umfassende grafische Sicht der Leistungsdaten, indem diese direkt der visuellen Struktur der Anwendung zugeordnet werden. In diesem Screenshot verschafft Ihnen der Abschnitt **CPU-Auslastung** von Visual Profiler eine genaue Aufschlüsselung der Nutzung von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Diensten eines Objekts, z.B. Rendering und Layout.  
  
 ![Visual Profiler-Anzeigeausgabe](./media/wpfperf-visualprofiler-04.png "WPFPerf_VisualProfiler_04")  
Visual Profiler-Anzeigeausgabe  
  
<a name="visual_rendering_behavior"></a>
## <a name="visual-rendering-behavior"></a>Verhalten des visuellen Renderings  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügt über Funktionen, die das Renderingverhalten visueller Objekte beeinflussen: Retained Mode-Grafiken, Vektorgrafiken und geräteunabhängige Grafiken.  
  
### <a name="retained-mode-graphics"></a>Retained Mode-Grafiken  
 Einer der Schlüssel zum Verständnis der Rolle des visuellen Objekts ist der Unterschied zwischen Grafiksystemen mit **Direktmodus** und **Retained Mode**. Eine standardmäßige Win32-Anwendung, die auf GDI oder GDI+ basiert, verwendet ein Grafiksystem mit unmittelbaren Modus. Das heißt, dass die Anwendung für das Neuzeichnen des Teils des Clientbereichs verantwortlich ist, der aufgrund einer Aktion, z.B. Änderung der Größe eines Fensters, oder eines Objekts, dessen visuelle Darstellung geändert wird, ungültig ist.  
  
 ![Diagramm der Win32-Renderingsequenz](./media/wpf-graphics-rendering-overview/win32-rendering-squence.png)  
  
 Im Gegensatz dazu verwendet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein System mit Retained Mode. Dies bedeutet, dass Objekte, die eine visuelle Darstellung haben, einen Satz serialisierter Zeichnungsdaten definieren. Nachdem die Zeichnungsdaten definiert wurden, ist das System für alle Repaint-Anforderungen zum Rendern der Anwendungsobjekte verantwortlich. Auch zur Laufzeit können Sie Anwendungsobjekte ändern oder erstellen und das System weiterhin auf Zeichnungsanforderungen reagieren lassen. Die Leistungsstärke eines Grafiksystems mit Retained Mode ist darauf zurückzuführen, dass Zeichnungsinformationen stets in einem serialisierten Zustand von der Anwendung gespeichert werden, die Verantwortung für das Rendering aber dem System überlassen wird. Das folgende Diagramm zeigt, wie die Anwendung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] auf Zeichnungsanforderungen reagieren lässt.  
  
 ![Diagramm der WPF-Renderingsequenz](./media/wpf-graphics-rendering-overview/wpf-rendering-sequence.png)  

#### <a name="intelligent-redrawing"></a>Intelligentes Neuzeichnen  
 Einer der größten Vorteile bei der Verwendung von Grafiken mit dem Retained Mode besteht darin, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] effizient optimieren kann, was in der Anwendung neu gezeichnet werden muss. Auch wenn Sie über eine komplexe Szene mit unterschiedlicher Deckkraft verfügen, müssen Sie im Allgemeinen nicht für besondere Zwecke Code zum Neuzeichnen optimieren. Vergleichen Sie dies mit der Win32-Programmierung, bei der Sie viele Ressourcen in die Optimierung Ihrer Anwendung durch Minimierung des Neuzeichnungaufwands im Aktualisierungsbereich investieren können. Ein Beispiel für den Typ der Komplexität in Verbindung mit der Optimierung der Neuzeichnung in Win32-Anwendungen finden Sie unter [Neuzeichnen im Aktualisierungsbereich](/windows/desktop/gdi/redrawing-in-the-update-region).  
  
### <a name="vector-graphics"></a>Vektorgrafiken  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet **Vektorgrafiken** als Renderingdatenformat. Vektorgrafiken – darunter Scalable Vector Graphics (SVG), Windows-Metadateien (WMF) und TrueType-Schriftarten – speichern Renderingdaten und übertragen sie als Liste von Anweisungen, die beschreiben, wie ein Bild mit Grafikprimitiven neu erstellt wird. TrueType-Schriftarten beispielsweise sind Umrissschriftarten, die einen Satz von Linien, Kurven und Befehlen anstelle eines Arrays von Pixeln beschreiben. Einer der wichtigsten Vorteile von Vektorgrafiken ist die Möglichkeit, auf eine beliebige Größe und Auflösung zu skalieren.  
  
 Im Gegensatz zu Vektorgrafiken speichern Bitmapgrafiken Renderingdaten als pixelweise Darstellung eines Bilds, die bereits für eine bestimmte Auflösung gerendert ist. Einer der wichtigsten Unterschiede zwischen Bitmap- und Vektorgrafikformaten ist die Originaltreue in Bezug auf das ursprüngliche Bild. Wenn beispielsweise die Größe eines Quellbilds geändert wird, strecken Bitmapgrafiksysteme das Bild, während Vektorgrafiksysteme das Bild skalieren und dabei die Bildtreue beibehalten.  
  
 Die folgende Abbildung zeigt ein Quellbild, dessen Größe um 300 % geändert wurde. Beachten Sie die Verzerrungen, die angezeigt werden, wenn das Quellbild als Bitmap-Grafik gestreckt und nicht als Vektorgrafikbild skaliert wird.  
  
 ![Unterschiede zwischen Raster- und Vektorgrafiken](./media/wpf-graphics-rendering-overview/raster-vector-differences.png)  
  
 Das folgende Markup <xref:System.Windows.Shapes.Path> zeigt zwei definierte Elemente. Das zweite Element <xref:System.Windows.Media.ScaleTransform> verwendet eine, um die Größe der Zeichnungsanweisungen des ersten Elements um 300 % zu ändern. Beachten Sie, dass <xref:System.Windows.Shapes.Path> die Zeichnungsanweisungen in den Elementen unverändert bleiben.  
  
 [!code-xaml[VectorGraphicsSnippets#VectorGraphicsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/VectorGraphicsSnippets/CS/PageOne.xaml#vectorgraphicssnippet1)]  
  
### <a name="about-resolution-and-device-independent-graphics"></a>Info zu auflösungs- und geräteunabhängiger Grafik  
 Zwei Systemfaktoren bestimmen die Größe von Text und Grafiken auf dem Bildschirm: Auflösung und DPI. Die Auflösung beschreibt die Anzahl der Pixel, die auf dem Bildschirm angezeigt werden. Mit höherer Auflösung werden Pixel kleiner und lassen Grafiken und Text kleiner erscheinen. Eine Grafik, die auf einem Monitor mit 1024 x 768 angezeigt wird, erscheint viel kleiner, wenn die Auflösung in 1600 x 1200 geändert wird.  
  
 Die andere Systemeinstellung, DPI, beschreibt die Größe eines Bildschirmzolls in Pixeln. Die meisten Windows-Systeme haben einen DPI von 96, was bedeutet, dass ein Bildschirmzoll 96 Pixel beträgt. Durch Erhöhen der DPI-Einstellung wird der Bildschirmzoll größer, durch Verringern des DPI-Werts wird der Bildschirmzoll kleiner. Das bedeutet, dass ein Bildschirmzoll nicht die gleiche Größe wie ein realer Zoll hat; auf den meisten System trifft dies wahrscheinlich zu. Wenn Sie den DPI-Wert erhöhen, werden mit DPI kompatible Grafiken und Text größer, da Sie den Bildschirmzoll vergrößert haben. Durch Erhöhen des DPI-Werts kann sich die Lesbarkeit von Text, besonders in hoher Auflösung, verbessern.  
  
 Nicht alle Programme sind DPI-kompatibel: Einige verwenden Hardwarepixel als primäre Maßeinheit. Eine Änderung des DPI-Systemwerts hat keine Auswirkungen auf diese Anwendungen. Viele andere Clientanwendungen verwenden Einheiten, die mit DPI kompatibel sind, um Schriftgrade zu beschreiben, aber verwenden Pixel, um alles andere zu beschreiben. Ein zu großer oder zu kleiner DPI-Wert kann zu Layoutproblemen für diese Anwendungen führen, da der Text der Anwendungen mit der DPI-Einstellung skaliert wird, während dies bei den Anwendungen der Benutzeroberfläche nicht der Fall ist. Das Problem wurde für mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] entwickelte Anwendungen gelöst.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt die automatische Skalierung mit geräteunabhängigen Pixeln als primärer Maßeinheit anstelle von Hardwarepixeln. Grafiken und Text skalieren ordnungsgemäß ohne zusätzlichen Eingriff seitens des Entwicklers der Anwendung. Die folgende Abbildung veranschaulicht anhand eines Beispiels, wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Text und -Grafiken mit unterschiedlichen DPI-Einstellungen angezeigt werden.  
  
 ![Grafiken und Text mit unterschiedlichen DPI-Einstellungen](./media/graphicsmm-dpi-setting-examples.png "graphicsmm_dpi_setting_examples")  
Grafiken und Text mit unterschiedlichen DPI-Einstellungen  
  
<a name="visualtreehelper_class"></a>
## <a name="visualtreehelper-class"></a>VisualTreeHelper-Klasse  
 Die <xref:System.Windows.Media.VisualTreeHelper> Klasse ist eine statische Hilfsklasse, die Low-Level-Funktionalität für die Programmierung auf der Ebene der visuellen Objekte bietet, was in sehr spezifischen Szenarien nützlich ist, z. B. beim Entwickeln von benutzerdefinierten Hochleistungssteuerelementen. In den meisten Fällen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bieten die übergeordneten Frameworkobjekte, wie <xref:System.Windows.Controls.Canvas> z. B. und <xref:System.Windows.Controls.TextBlock>, eine größere Flexibilität und Benutzerfreundlichkeit.  
  
### <a name="hit-testing"></a>Treffertests  
 Die <xref:System.Windows.Media.VisualTreeHelper> Klasse stellt Methoden zum Treffertesten für visuelle Objekte bereit, wenn die standardmäßige Treffertestunterstützung nicht Ihren Anforderungen entspricht. Sie können <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> die Methoden <xref:System.Windows.Media.VisualTreeHelper> in der Klasse verwenden, um zu bestimmen, ob sich eine Geometrie oder ein Punktkoordinatenwert innerhalb der Grenze eines bestimmten Objekts befindet, z. B. eines Steuerelements oder Eines Grafikelements. Sie können beispielsweise mit Treffertests bestimmen, ob ein Mausklick innerhalb des umschließenden Rechtecks eines Objekts innerhalb der Geometrie eines Kreises liegt. Außerdem können Sie angeben, dass die standardmäßige Implementierung des Treffertests Ihre eigenen benutzerdefinierten Treffertestberechnungen überschreibt.  
  
 Weitere Informationen zu Treffertests finden Sie unter [Treffertests in der visuellen Ebene](hit-testing-in-the-visual-layer.md).  
  
### <a name="enumerating-the-visual-tree"></a>Auflisten der visuellen Struktur  
 Die <xref:System.Windows.Media.VisualTreeHelper> Klasse bietet Funktionen zum Aufzählen der Member einer visuellen Struktur. Um ein übergeordnetes <xref:System.Windows.Media.VisualTreeHelper.GetParent%2A> Element abzurufen, rufen Sie die Methode auf. Um ein untergeordnetes oder direktes untergeordnetes Element <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A> eines visuellen Objekts abzurufen, rufen Sie die Methode auf. Diese Methode gibt <xref:System.Windows.Media.Visual> ein untergeordnetes Element des übergeordneten Elements im angegebenen Index zurück.  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie alle Nachfolgerelemente eines visuellen Objekts auflisten. Diese Methode können Sie verwenden, wenn Sie alle Renderinginformationen einer Hierarchie von visuellen Objekten serialisieren möchten.  
  
 [!code-csharp[VisualsOverview#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#101)]
 [!code-vb[VisualsOverview#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#101)]  
  
 In den meisten Fällen ist die logische Struktur eine sinnvollere Darstellung der Elemente in einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung. Obwohl Sie die logische Struktur nicht ändern, ist diese Ansicht der Anwendung nützlich, um die Vererbung von Eigenschaften und das Ereignisrouting nachzuvollziehen. Im Gegensatz zur visuellen Struktur kann die logische Struktur <xref:System.Windows.Documents.ListItem>nicht-visuelle Datenobjekte darstellen, z. B. . Weitere Informationen zu der logischen Struktur finden Sie unter [Strukturen in WPF](../advanced/trees-in-wpf.md).  
  
 Die <xref:System.Windows.Media.VisualTreeHelper> Klasse stellt Methoden zum Zurückgeben des umgrenzenden Rechtecks visueller Objekte bereit. Sie können das umgebende Rechteck eines <xref:System.Windows.Media.VisualTreeHelper.GetContentBounds%2A>visuellen Objekts zurückgeben, indem Sie aufrufen. Sie können das umgebende Rechteck aller abhängigen Elemente eines visuellen Objekts, einschließlich des visuellen Objekts selbst, zurückgeben, indem Sie <xref:System.Windows.Media.VisualTreeHelper.GetDescendantBounds%2A>aufrufen. Der folgende Code zeigt, wie Sie das umschließende Rechteck des visuellen Objekts und aller Nachfolgerknoten berechnen.  
  
 [!code-csharp[VisualsOverview#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#102)]
 [!code-vb[VisualsOverview#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#102)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Visual>
- <xref:System.Windows.Media.VisualTreeHelper>
- <xref:System.Windows.Media.DrawingVisual>
- [2D-Grafiken und Bildverarbeitung](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Treffertests in der visuellen Ebene](hit-testing-in-the-visual-layer.md)
- [Verwenden von DrawingVisual-Objekten](using-drawingvisual-objects.md)
- [Lernprogramm: Hosten von visuellen Objekten in einer Win32-Anwendung](tutorial-hosting-visual-objects-in-a-win32-application.md)
- [Optimieren der WPF-Anwendungsleistung](../advanced/optimizing-wpf-application-performance.md)
