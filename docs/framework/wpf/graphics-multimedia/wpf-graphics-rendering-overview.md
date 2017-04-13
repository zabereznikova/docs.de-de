---
title: "&#220;bersicht &#252;ber das WPF-Grafikrendering | Microsoft Docs"
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
  - "Grafiken, Rendering"
  - "Rendern von Grafiken"
ms.assetid: 6dec9657-4d8c-4e46-8c54-40fb80008265
caps.latest.revision: 51
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 48
---
# &#220;bersicht &#252;ber das WPF-Grafikrendering
Dieses Thema enthält eine Übersicht über die visuelle Ebene von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Der Schwerpunkt liegt dabei auf der Rolle der <xref:System.Windows.Media.Visual>\-Klasse für die Renderingunterstützung im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Modell.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="role_of_visual_object"></a>   
## Rolle des visuellen Objekts  
 Die <xref:System.Windows.Media.Visual>\-Klasse ist die grundlegende Abstraktion, von der jedes <xref:System.Windows.FrameworkElement>\-Objekt abgeleitet ist.  Sie dient außerdem als Einstiegspunkt zum Schreiben neuer Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], und in Vielem kann sie als das Fensterhandle \(HWND\) im Win32\-Anwendungsmodell betrachtet werden.  
  
 Das <xref:System.Windows.Media.Visual>\-Objekt ist ein zentrales [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Objekt, dessen primäre Rolle die Unterstützung des Rendering ist.  Steuerelemente der Benutzeroberfläche, wie <xref:System.Windows.Controls.Button> und <xref:System.Windows.Controls.TextBox>, werden von der <xref:System.Windows.Media.Visual>\-Klasse abgeleitet und verwenden diese zum Beibehalten ihrer Renderingdaten.  Das <xref:System.Windows.Media.Visual>\-Objekt unterstützt folgende Vorgänge:  
  
-   Ausgabeanzeige: Rendern des beibehaltenen, serialisierten Zeichnungsinhalts eines visuellen Objekts.  
  
-   Transformationen: Ausführen von Transformationen für ein visuelles Element.  
  
-   Clipping: Bereitstellen von Clippingbereichunterstützung für ein visuelles Objekt.  
  
-   Treffertests: Bestimmen, ob eine Koordinate oder eine Geometrie innerhalb der Grenzen eines visuellen Objekts enthalten ist.  
  
-   Berechnungen für umgebende Felder: Bestimmen des umgebenden Rechtecks eines visuellen Objekts.  
  
 Das <xref:System.Windows.Media.Visual>\-Objekt umfasst jedoch keine Unterstützung für Features außerhalb des Rendering, z. B.:  
  
-   Ereignisbehandlung  
  
-   Layout  
  
-   Stile  
  
-   Datenbindung  
  
-   Globalisierung  
  
 <xref:System.Windows.Media.Visual> wird als öffentliche abstrakte Klasse verfügbar gemacht, von der untergeordnete Klassen abgeleitet werden müssen.  Die folgende Abbildung zeigt die Hierarchie der visuellen Objekte, die in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügbar gemacht werden.  
  
 ![Diagramm der vom Visual&#45;Objekt abgeleiteten Klassen](../../../../docs/framework/wpf/graphics-multimedia/media/visualclass01.png "VisualClass01")  
  
        Hierarchie der Visual\-Klasse  
  
### DrawingVisual\-Klasse  
 <xref:System.Windows.Media.DrawingVisual> ist eine einfache Zeichnungsklasse, die verwendet wird, um Formen, Bilder oder Text zu rendern.  Diese Klasse wird als einfach angesehen, weil sie weder Layout noch Ereignisbehandlung bereitstellt. Dadurch wird die Laufzeitleistung gesteigert.  Aus diesem Grund sind Zeichnungen ideal für Hintergründe und ClipArt.  <xref:System.Windows.Media.DrawingVisual> kann verwendet werden, um ein benutzerdefiniertes visuelles Objekt zu erstellen.  Weitere Informationen finden Sie unter [Verwenden von DrawingVisual\-Objekten](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  
  
### Viewport3DVisual\-Klasse  
 <xref:System.Windows.Media.Media3D.Viewport3DVisual> bildet eine Brücke zwischen <xref:System.Windows.Media.Visual>\-2D\-Objekten und <xref:System.Windows.Media.Media3D.Visual3D>\-Objekten.  Die <xref:System.Windows.Media.Media3D.Visual3D>\-Klasse ist die Basisklasse für alle visuellen 3D\-Elemente.  Für <xref:System.Windows.Media.Media3D.Viewport3DVisual> müssen ein <xref:System.Windows.Media.Media3D.Viewport3DVisual.Camera%2A>\-Wert und ein <xref:System.Windows.Media.Media3D.Viewport3DVisual.Viewport%2A>\-Wert definiert werden.  Die Kamera ermöglicht Ihnen die Anzeige der Szene.  Der Viewport legt fest, wo die Projektion auf die 2D\-Oberfläche abgebildet wird.  Weitere Informationen über 3D in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Übersicht über 3D\-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md).  
  
### ContainerVisual\-Klasse  
 Die <xref:System.Windows.Media.ContainerVisual>\-Klasse wird als Container für eine Auflistung von <xref:System.Windows.Media.Visual>\-Objekten verwendet.  Die <xref:System.Windows.Media.DrawingVisual>\-Klasse wird aus der <xref:System.Windows.Media.ContainerVisual>\-Klasse abgeleitet, womit sie eine Auflistung von visuellen Objekten enthalten kann.  
  
### Zeichnungsinhalt in visuellen Objekten  
 Ein <xref:System.Windows.Media.Visual>\-Objekt speichert seine Renderingdaten als **Anweisungsliste für Vektorgrafiken**.  Jedes Element in der Anweisungsliste stellt einen Low\-Level\-Satz mit Grafikdaten und dazugehörigen Ressourcen in einem serialisierten Format dar.  Es gibt vier verschiedene Typen von Renderingdaten, die Zeichnungsinhalt enthalten können.  
  
|Zeichnungsinhaltstyp|Beschreibung|  
|--------------------------|------------------|  
|Vektorgrafik|Stellt Vektorgrafikdaten und dazugehörige <xref:System.Windows.Media.Brush>\-Informationen und <xref:System.Windows.Media.Pen>\-Informationen dar.|  
|Bild|Stellt ein Bild innerhalb eines von einer <xref:System.Windows.Rect>\-Struktur definierten Bereichs dar.|  
|Symbol|Stellt eine Zeichnung dar, die eine als <xref:System.Windows.Media.GlyphRun> bezeichnete Symbolfolge aus einer angegebenen Schriftartressource rendert.  Auf diese Weise wird Text dargestellt.|  
|Video|Stellt eine Zeichnung dar, die Video rendert.|  
  
 Mit <xref:System.Windows.Media.DrawingContext> können Sie ein <xref:System.Windows.Media.Visual>\-Objekt mit visuellem Inhalt auffüllen.  Wenn Sie die Zeichnungsbefehle eines <xref:System.Windows.Media.DrawingContext>\-Objekts verwenden, speichern Sie einen Satz von Renderingdaten, die später vom Grafiksystem verwendet werden. Sie zeichnen nicht in Echtzeit auf dem Bildschirm.  
  
 Wenn Sie ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelement, z. B. ein <xref:System.Windows.Controls.Button>\-Steuerelement, erstellen, generiert es implizit Renderingdaten für die eigene Darstellung.  Wenn Sie z. B. die <xref:System.Windows.Controls.ContentControl.Content%2A>\-Eigenschaft des <xref:System.Windows.Controls.Button>\-Steuerelements festlegen, wird es zur Speicherung einer Renderingdarstellung eines Symbols veranlasst.  
  
 Ein <xref:System.Windows.Media.Visual> beschreibt den eigenen Inhalt als ein oder mehrere <xref:System.Windows.Media.Drawing>\-Objekte, die in einer <xref:System.Windows.Media.DrawingGroup> enthalten sind.  Eine <xref:System.Windows.Media.DrawingGroup> beschreibt außerdem Durchlässigkeitsmasken, Transformationen, Bitmapeffekte und andere Vorgänge, die auf ihre Inhalte angewendet werden.  <xref:System.Windows.Media.DrawingGroup>\-Vorgänge werden beim Rendering von Inhalt in der folgenden Reihenfolge angewendet: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> und dann <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 Die folgende Abbildung zeigt die Reihenfolge, in der <xref:System.Windows.Media.DrawingGroup>\-Vorgänge während der Renderingsequenz angewendet werden.  
  
 ![DrawingGroup&#45;Reihenfolge der Vorgänge](../../../../docs/framework/wpf/graphics-multimedia/media/graphcismm-drawinggroup-order.png "graphcismm\_drawinggroup\_order")  
  
        Reihenfolge von DrawingGroup\-Vorgängen  
  
 Weitere Informationen finden Sie unter [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
#### Zeichnungsinhalt auf der Visual\-Ebene  
 Ein <xref:System.Windows.Media.DrawingContext> wird niemals direkt instanziiert. Sie können jedoch mit bestimmten Methoden, z. B. <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=fullName> und <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=fullName>, einen Zeichnungskontext abrufen.  Im folgenden Beispiel wird ein <xref:System.Windows.Media.DrawingContext> aus einem <xref:System.Windows.Media.DrawingVisual> abgerufen und zum Zeichnen eines Rechtecks verwendet.  
  
 [!code-csharp[drawingvisualsample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[drawingvisualsample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
#### Auflisten von Zeichnungsinhalt auf der Visual\-Ebene  
 Neben ihren anderen Verwendungszwecken stellen die <xref:System.Windows.Media.Drawing>\-Objekte auch ein Objektmodell für die Auflistung der Inhalte von einem <xref:System.Windows.Media.Visual> bereit.  
  
> [!NOTE]
>  Wenn Sie den Visualinhalt auflisten, rufen Sie <xref:System.Windows.Media.Drawing>\-Objekte ab, und nicht die zugrunde liegende Darstellung der Renderingdaten als Anweisungsliste für Vektorgrafiken.  
  
 Im folgenden Beispiel wird mit der <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A>\-Methode der <xref:System.Windows.Media.DrawingGroup>\-Wert von einem <xref:System.Windows.Media.Visual> abgerufen und aufgelistet.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
<a name="how_visual_objects_are_used_to_build_controls"></a>   
## So werden visuelle Objekte zum Erstellen von Steuerelementen verwendet  
 Viele Objekte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bestehen aus anderen visuellen Objekten, d. h., sie können unterschiedliche Hierarchien von Nachfolgerobjekten enthalten.  Zahlreiche Benutzeroberflächenelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], z. B. Steuerelemente, bestehen aus mehreren visuellen Objekten, die verschiedene Typen von Renderingelementen darstellen.  Zum Beispiel kann das <xref:System.Windows.Controls.Button>\-Steuerelement eine Anzahl anderer Objekte enthalten, einschließlich <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>, <xref:System.Windows.Controls.ContentPresenter> und <xref:System.Windows.Controls.TextBlock>.  
  
 Der folgende Code zeigt ein in Markup definiertes <xref:System.Windows.Controls.Button>\-Steuerelement.  
  
 [!code-xml[VisualsOverview#VisualsOverviewSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet1)]  
  
 Wenn Sie die visuellen Objekte auflisten sollten, aus denen das <xref:System.Windows.Controls.Button>\-Standardsteuerelement besteht, würden Sie die nachfolgend dargestellte Hierarchie der visuellen Objekte vorfinden:  
  
 ![Diagramm der visuellen Strukturhierarchie](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview03.png "VisualLayerOverview03")  
  
        Diagramm der Hierarchie der visuellen Struktur  
  
 Das <xref:System.Windows.Controls.Button>\-Steuerelement enthält ein <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>\-Element, das wiederum ein <xref:System.Windows.Controls.ContentPresenter>\-Element enthält.  Das <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>\-Element ist dafür verantwortlich, einen Rahmen und einen Hintergrund für das <xref:System.Windows.Controls.Button>\-Steuerelement zu zeichnen.  Das <xref:System.Windows.Controls.ContentPresenter>\-Element ist dafür verantwortlich, den Inhalt des <xref:System.Windows.Controls.Button>\-Steuerelements anzuzeigen.  Da Sie Text anzeigen, enthält das <xref:System.Windows.Controls.ContentPresenter>\-Element in diesem Fall ein <xref:System.Windows.Controls.TextBlock>\-Element.  Der Umstand, dass das <xref:System.Windows.Controls.Button>\-Steuerelement ein <xref:System.Windows.Controls.ContentPresenter>\-Element verwendet, bedeutet, dass der Inhalt durch andere Elemente dargestellt werden könnte, z. B. ein <xref:System.Windows.Controls.Image> oder eine Geometrie, z. B. eine <xref:System.Windows.Media.EllipseGeometry>.  
  
### Steuerelementvorlagen  
 Der Schlüssel zur Erweiterung eines Steuerelements in eine Hierarchie von Steuerelementen ist die <xref:System.Windows.Controls.ControlTemplate>.  Eine Steuerelementvorlage gibt die visuelle Standardhierarchie für ein Steuerelement an.  Wenn Sie ein Steuerelement explizit mit Verweisen versehen, versehen Sie seine visuelle Hierarchie implizit mit Verweisen.  Sie können die Standardwerte für eine Steuerelementvorlage überschreiben, um eine angepasste visuelle Darstellung für ein Steuerelement zu erstellen.  Sie könnten z. B. den Hintergrundfarbwert des <xref:System.Windows.Controls.Button>\-Steuerelements so ändern, dass es einen Wert für einen linearen Farbverlauf statt eines Werts für eine Volltonfarbe verwendet.  Weitere Informationen hierzu finden Sie unter [Button\-Stile und \-Vorlagen](../../../../docs/framework/wpf/controls/button-styles-and-templates.md).  
  
 Ein Element der Benutzeroberfläche, z. B. ein <xref:System.Windows.Controls.Button>\-Steuerelement, enthält mehrere Anweisungslisten für Vektorgrafiken, die die gesamte Renderingdefinition eines Steuerelements beschreiben.  Der folgende Code zeigt ein in Markup definiertes <xref:System.Windows.Controls.Button>\-Steuerelement.  
  
 [!code-xml[VisualsOverview#VisualsOverviewSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet2)]  
  
 Wenn Sie die visuellen Objekte und die Anweisungslisten für Vektorgrafiken auflisten sollten, aus denen das <xref:System.Windows.Controls.Button>\-Standardsteuerelement besteht, würden Sie die nachfolgend dargestellte Hierarchie der visuellen Objekte vorfinden:  
  
 ![Diagramm der visuellen Struktur und des Renderings von Daten](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview04.png "VisualLayerOverview04")  
  
        Diagramm der visuellen Struktur und der Renderingdaten  
  
 Das <xref:System.Windows.Controls.Button>\-Steuerelement enthält ein <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>\-Element, das wiederum ein <xref:System.Windows.Controls.ContentPresenter>\-Element enthält.  Das <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>\-Element ist dafür verantwortlich, alle diskreten Grafikelemente zu zeichnen, aus denen der Rahmen und der Hintergrund einer Schaltfläche bestehen.  Das <xref:System.Windows.Controls.ContentPresenter>\-Element ist dafür verantwortlich, den Inhalt des <xref:System.Windows.Controls.Button>\-Steuerelements anzuzeigen.  Da Sie ein Bild anzeigen, enthält das <xref:System.Windows.Controls.ContentPresenter>\-Element in diesem Fall ein <xref:System.Windows.Controls.Image>\-Element.  
  
 Im Zusammenhang mit der Hierarchie von visuellen Objekten und Anweisungslisten für Vektorgrafiken sind ein paar Punkte zu beachten:  
  
-   Die Reihenfolge in der Hierarchie stellt die Renderingreihenfolge der Zeichnungsinformationen dar.  Vom visuellen Stammelement werden untergeordnete Elemente von links nach rechts und von oben nach unten traversiert.  Wenn ein Element über visuelle untergeordnete Elemente verfügt, werden sie vor den Geschwistern des Elements traversiert.  
  
-   Elemente in der Hierarchie, die keine Blattknoten sind, z. B. <xref:System.Windows.Controls.ContentPresenter>, werden für die Aufnahme von untergeordneten Elementen verwendet. Sie enthalten keine Anweisungslisten.  
  
-   Wenn ein visuelles Element sowohl eine Anweisungsliste für Vektorgrafiken als auch untergeordnete visuelle Elemente enthält, wird die Anweisungsliste im übergeordneten visuellen Element vor Zeichnungen in einem der untergeordneten visuellen Objekte gerendert.  
  
-   Die Elemente in der Anweisungsliste für Vektorgrafiken werden von links nach rechts gerendert.  
  
<a name="visual_tree"></a>   
## Visuelle Struktur  
 Die visuelle Struktur enthält alle visuellen Elemente, die in der Benutzeroberfläche einer Anwendung verwendet werden.  Da ein visuelles Element beibehaltene Zeichnungsinformationen enthält, können Sie sich die visuelle Struktur als ein Szenendiagramm vorstellen, das alle Renderinginformationen enthält, die zum Zusammensetzen der Ausgabe für das Anzeigegerät benötigt werden.  Diese Struktur ist die Ansammlung aller visuellen Elemente, die direkt von der Anwendung erstellt werden, ob in Code oder Markup.  Die visuelle Struktur enthält außerdem alle visuellen Elemente, die von der Vorlagenerweiterung von Elementen wie Steuerelementen und Datenobjekten erstellt werden.  
  
 Der folgende Code zeigt ein in Markup definiertes <xref:System.Windows.Controls.StackPanel>\-Element.  
  
 [!code-xml[VisualsOverview#VisualsOverviewSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet3)]  
  
 Wenn Sie die visuellen Objekte auflisten sollten, aus denen das <xref:System.Windows.Controls.StackPanel>\-Element im Markupbeispiel besteht, würden Sie die nachfolgend dargestellte Hierarchie der visuellen Objekte vorfinden:  
  
 ![Diagramm der visuellen Strukturhierarchie](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview05.png "VisualLayerOverview05")  
  
        Diagramm der Hierarchie der visuellen Struktur  
  
### Renderingreihenfolge  
 Die visuelle Struktur bestimmt die Renderingreihenfolge von visuellen Objekten und Zeichnungsobjekten in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Die Traversierreihenfolge beginnt mit dem visuellen Stammelement, dem obersten Knoten in der visuellen Struktur.  Anschließend werden die untergeordneten Elemente des visuellen Stammelements von links nach rechts traversiert.  Wenn ein visuelles Objekt untergeordnete Elemente hat, werden diese vor den Geschwistern des visuellen Objekts traversiert.  Das heißt, dass der Inhalt eines untergeordneten visuellen Elements vor dem Inhalt des visuellen Objekts selbst gerendert wird.  
  
 ![Diagramm der visuellen Struktur&#45;Rendering&#45;Reihenfolge](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview06.png "VisualLayerOverview06")  
  
        Diagramm der Renderingreihenfolge der visuellen Struktur  
  
### Visuelles Stammelement  
 Das **visuelle Stammelement** ist das oberste Element in der Hierarchie einer visuellen Struktur.  In den meisten Anwendungen ist die Basisklasse des visuellen Stammelements entweder <xref:System.Windows.Window> oder <xref:System.Windows.Navigation.NavigationWindow>.  Wenn Sie aber visuelle Objekte in einer Win32\-Anwendung hosten würden, wäre das visuelle Stammelement das oberste im Win32\-Fenster gehostete visuelle Objekt.  Weitere Informationen hierzu finden Sie unter [Lernprogramm: Hosten von visuellen Objekten in einer Win32\-Anwendung](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md).  
  
### Beziehung zur logischen Struktur  
 Die logische Struktur in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt die Elemente einer Anwendung zur Laufzeit dar.  Auch wenn Sie diese Struktur nicht direkt ändern, ist diese Ansicht der Anwendung hilfreich, um Eigenschaftenvererbung und Ereignisrouting zu verstehen.  Im Gegensatz zur visuellen Struktur kann die logische Struktur nicht visuelle Datenobjekte, z. B. <xref:System.Windows.Documents.ListItem>, darstellen.  In vielen Fällen sind die logische Struktur und die Markupdefinitionen einer Anwendung nahezu deckungsgleich.  Der folgende Code zeigt ein in Markup definiertes <xref:System.Windows.Controls.DockPanel>\-Element.  
  
 [!code-xml[VisualsOverview#VisualsOverviewSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet5)]  
  
 Wenn Sie die logischen Objekte auflisten sollten, aus denen das <xref:System.Windows.Controls.DockPanel>\-Element im Markupbeispiel besteht, würden Sie die nachfolgend dargestellte Hierarchie der logischen Objekte vorfinden:  
  
 ![Baumstrukturdiagramm](../../../../docs/framework/wpf/graphics-multimedia/media/tree1-wcp.png "Tree1\_wcp")  
  
        Diagramm der logischen Struktur  
  
 Die visuelle Struktur und die logische Struktur werden mit dem aktuellen Satz der Anwendungselemente synchronisiert und spiegeln so jede Aufnahme, Löschung oder Änderung eines Elements wider.  Die Strukturen liefern aber verschiedene Ansichten der Anwendung.  Im Gegensatz zur visuellen Struktur erweitert die logische Struktur nicht das <xref:System.Windows.Controls.ContentPresenter>\-Element eines Steuerelements.  Das heißt, es gibt für denselben Objektsatz keine direkte 1:1\-Entsprechung zwischen einer logischen Struktur und einer visuellen Struktur.  Wenn für das **LogicalTreeHelper**\-Objekt die <xref:System.Windows.LogicalTreeHelper.GetChildren%2A>\-Methode und für das **VisualTreeHelper**\-Objekt die <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A>\-Methode aufgerufen und dasselbe Element als Parameter verwendet wird, führt dies sogar zu unterschiedlichen Ergebnissen.  
  
 Weitere Informationen über die logische Struktur finden Sie unter [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
### Anzeigen der visuellen Struktur mit XamlPad  
 Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Tool XamlPad ermöglicht das Anzeigen und Durchsuchen der visuellen Struktur, die dem aktuell definierten [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]\-Inhalt entspricht.  Klicken Sie auf der Menüleiste auf die Schaltfläche **Visuelle Struktur anzeigen**, um die visuelle Struktur anzuzeigen.  Die folgende Abbildung zeigt die Erweiterung des [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]\-Inhalts in die Knoten der visuellen Struktur im Bereich **Visual Tree Explorer** von XamlPad:  
  
 ![Visueller Struktur&#45;Explorer&#45;Bereich in XamlPad](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview08.png "VisualLayerOverview08")  
  
        Bereich Visual Tree Explorer in XamlPad  
  
 Beachten Sie, dass die Steuerelemente <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.Button> jeweils eine eigene Hierarchie der visuellen Objekte im Bereich **Visual Tree Explorer** von XamlPad anzeigen.  Das liegt daran, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelemente über eine <xref:System.Windows.Controls.ControlTemplate> verfügen, die die visuelle Struktur dieses Steuerelements enthält.  Wenn Sie ein Steuerelement explizit mit Verweisen versehen, versehen Sie seine visuelle Hierarchie implizit mit Verweisen.  
  
### Erstellen von visuellen Leistungsprofilen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt eine Suite von Tools zum Erstellen von Leistungsprofilen bereit, mit denen Sie das Laufzeitverhalten einer Anwendung analysieren und die Typen der anwendbaren Leistungsoptimierungen bestimmen können.  Das Tool Visual Profiler bietet eine umfangreiche grafische Ansicht der Leistungsdaten. Dazu wird eine direkte Zuordnung zur visuellen Struktur der Anwendung vorgenommen.  In dieser Bildschirmaufnahme enthält der Abschnitt **CPU\-Verwendung** von Visual Profiler eine genaue Aufschlüsselung der Nutzung von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Diensten, z. B. Rendering und Layout, durch ein Objekt.  
  
 ![Visual Profiler&#45;Anzeigeausgabe](../../../../docs/framework/wpf/graphics-multimedia/media/wpfperf-visualprofiler-04.png "WPFPerf\_VisualProfiler\_04")  
Ausgabe von Visual Profiler  
  
<a name="visual_rendering_behavior"></a>   
## Visuelles Renderingverhalten  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] führt eine Reihe von Features ein, die das Renderingverhalten visueller Objekte beeinflussen: Grafiken mit Speichermodus, Vektorgrafiken und geräteunabhängige Grafiken.  
  
### Grafiken mit Speichermodus  
 Einer der Schlüssel zum Verstehen der Rolle von visuellen Objekten besteht darin, den Unterschied zwischen Grafiksystemen mit **unmittelbarem Modus** und Grafiksystemen mit **Speichermodus** zu verstehen.  Eine Win32\-Standardanwendung, die auf GDI oder GDI\+ basiert, verwendet ein Grafiksystem mit unmittelbarem Modus.  Das heißt, die Anwendung ist dafür verantwortlich, den Teil des Clientbereichs neu zu zeichnen, der durch eine Aktion wie die Änderung der Größe eines Fensters oder der visuellen Darstellung eines Objekts ungültig gemacht wird.  
  
 ![Diagramm der Win32&#45;Renderingsequenz](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview01.png "VisualLayerOverview01")  
  
        Diagramm der Win32\-Renderingsequenz  
  
 Im Gegensatz dazu verwendet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein System mit Speichermodus.  Das heißt, dass Anwendungsobjekte mit einer visuellen Darstellung einen Satz serialisierter Zeichnungsdaten definieren.  Nachdem die Zeichnungsdaten definiert wurden, ist das System bei allen Neuzeichnungsanforderungen für das Rendering der Anwendungsobjekte verantwortlich.  Selbst zur Laufzeit können Sie Anwendungsobjekte ändern oder erstellen und sich trotzdem darauf verlassen, dass das System auf Zeichnungsanforderungen reagiert.  Die Leistung eines Grafiksystems mit Speichermodus besteht darin, dass die Zeichnungsinformationen von der Anwendung immer in einem serialisierten Zustand beibehalten werden, die Verantwortung für das Rendering aber beim System verbleibt.  Das folgende Diagramm zeigt, wie sich die Anwendung für die Reaktion auf Zeichnungsanforderungen auf [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verlässt.  
  
 ![Diagramm der WPF&#45;Renderingsequenz](../../../../docs/framework/wpf/graphics-multimedia/media/visuallayeroverview02.png "VisualLayerOverview02")  
  
        Diagramm der WPF\-Renderingsequenz  
  
#### Intelligentes Neuzeichnen  
 Einer der größten Vorteile bei der Verwendung von Grafiken mit Speichermodus besteht darin, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das, was in der Anwendung neu gezeichnet werden muss, effizient optimieren kann.  Auch bei einer komplexen Szene mit verschiedenen Durchlässigkeitsgraden müssen Sie im Allgemeinen keinen Code für besondere Zwecke schreiben, um das Neuzeichnen zu optimieren.  Vergleichen Sie dies mit der Win32\-Programmierung, bei der Sie möglicherweise zur Optimierung Ihrer Anwendung mit großem Aufwand das Neuzeichnen im Aktualisierungsbereich auf ein Minimum zurückführen müssen.  Unter [Neuzeichnen im Aktualisierungsbereich](_win32_Redrawing_in_the_Update_Region) finden Sie ein Beispiel dafür, wie komplex das Optimieren des Neuzeichnens in Win32\-Anwendungen sein kann.  
  
### Vektorgrafiken  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet **Vektorgrafiken** als Renderingdatenformat.  Vektorgrafiken – dazu gehören skalierbare Vektorgrafiken \(SVG\), Windows\-Metadateien \(WMF\) und TrueType\-Schriftarten – speichern Renderingdaten und übertragen sie als Liste mit Anweisungen, die beschreiben, wie ein Bild mit Grafikprimitiven neu erstellt wird.  Bei TrueType\-Schriftarten handelt es sich z. B. um Outlineschriftarten, die statt eines Pixelarrays einen Satz von Linien, Kurven und Befehlen beschreiben.  Einer der zentralen Vorteile von Vektorgrafiken ist die Möglichkeit, sie auf eine beliebige Größe und Auflösung zu skalieren.  
  
 Im Gegensatz zu Vektorgrafiken speichern Bitmapgrafiken Renderingdaten als pixelweise, vorab für eine bestimmte Auflösung gerenderte Darstellung eines Bilds.  Einer der wichtigsten Unterschiede zwischen Bitmap\- und Vektorgrafikformaten ist die Wiedergabetreue im Verhältnis zum ursprünglichen Quellbild.  Wenn z. B. die Größe eines Quellbilds geändert wird, strecken Bitmapgrafiksysteme das Bild, während Vektorgrafiksysteme das Bild skalieren und so die Wiedergabetreue für das Bild erhalten.  
  
 Die folgende Abbildung zeigt ein Quellbild, das um 300 % vergrößert wurde.   Beachten Sie die Verzerrungen, die entstehen, wenn das Quellbild als Bitmapgrafik gestreckt und nicht als Vektorgrafikbild skaliert wird.  
  
 ![Unterschiede zwischen Raster&#45; und Vektorgrafiken](../../../../docs/framework/wpf/graphics-multimedia/media/vectorgraphics01.png "VectorGraphics01")  
  
        Unterschiede zwischen Raster\- und Vektorgrafiken  
  
 Das folgende Markup zeigt zwei definierte <xref:System.Windows.Shapes.Path>\-Elemente.  Das zweite Elemente ändert mit <xref:System.Windows.Media.ScaleTransform> die Größe in den Zeichnungsanweisungen des ersten Elements um 300 %.  Beachten Sie, dass die Zeichnungsanweisungen in den <xref:System.Windows.Shapes.Path>\-Elementen unverändert bleiben.  
  
 [!code-xml[VectorGraphicsSnippets#VectorGraphicsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VectorGraphicsSnippets/CS/PageOne.xaml#vectorgraphicssnippet1)]  
  
### Informationen über Auflösung und geräteunabhängige Grafiken  
 Es gibt zwei Systemfaktoren, die die Größe von Text und Grafiken auf dem Bildschirm bestimmen: Auflösung und DPI.  Mit Auflösung wird die Anzahl der auf dem Bildschirm angezeigten Pixel beschrieben.  Mit höherer Auflösung werden Pixel kleiner und lassen Grafiken und Text kleiner erscheinen.  Eine Grafik, die auf einem Monitor mit 1024 x 768 angezeigt wird, erscheint viel kleiner, wenn die Auflösung in 1600 x 1200 geändert wird.  
  
 Die andere Systemeinstellung, DPI, beschreibt die Größe eines Bildschirmzolls in Pixeln.  Die meisten [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]\-Systeme besitzen 96 DPI, d. h., ein Bildschirmzoll enthält 96 Pixel.  Durch Erhöhen der DPI\-Einstellung wird der Bildschirmzoll größer, durch Verringern kleiner.  Das heißt, die Größe eines Bildschirmzolls entspricht nicht der eines Zolls in der realen Welt \(das trifft wahrscheinlich auf die meisten Systeme zu\).  Wenn Sie die DPI\-Einstellung erhöhen, werden Grafiken und Text, die diesen Wert berücksichtigen, größer, da Sie den Bildschirmzoll vergrößert haben.  Die Erhöhung der DPI\-Einstellung kann insbesondere bei hohen Auflösungen die Lesbarkeit des Textes verbessern.  
  
 Nicht alle Anwendungen berücksichtigen die DPI\-Einstellung: Einige verwenden Hardwarepixel als primäre Maßeinheit, und die Änderung der DPI\-Einstellung des Systems hat auf diese Anwendungen keine Auswirkungen.  Viele andere Anwendungen verwenden Einheiten, die die DPI\-Einstellung berücksichtigen, zur Beschreibung von Schriftgraden, aber Pixel zur Beschreibung von allem anderen.  Eine zu niedrige oder zu hohe DPI\-Einstellung kann bei diesen Anwendungen zu Layoutproblemen führen, da der Text der Anwendung mit der DPI\-Einstellung des Systems skaliert wird, die Benutzeroberfläche der Anwendung hingegen nicht.  Dieses Problem tritt nicht mehr bei Anwendungen auf, die mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] entwickelt wurden.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt die automatische Skalierung, indem statt Hardwarepixel geräteunabhängige Pixel als primäre Maßeinheit verwendet werden. Grafiken und Text werden ohne zusätzliche Bearbeitung durch die Anwendungsentwickler ordnungsgemäß skaliert.  Die folgende Abbildung zeigt ein Beispiel dafür, wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Text und \-Grafiken bei unterschiedlichen DPI\-Einstellungen angezeigt werden.  
  
 ![Grafiken und Text mit unterschiedlichen DPI&#45;Einstellungen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-dpi-setting-examples.png "graphicsmm\_dpi\_setting\_examples")  
  
        Grafiken und Text bei verschiedenen DPI\-Einstellungen  
  
<a name="visualtreehelper_class"></a>   
## VisualTreeHelper\-Klasse  
 Die <xref:System.Windows.Media.VisualTreeHelper>\-Klasse ist eine statische Hilfsklasse, die Low\-Level\-Funktionen für die Programmierung auf der Ebene der visuellen Objekte bereitstellt. Das ist in sehr spezifischen Szenarien hilfreich, z. B. bei der Entwicklung von benutzerdefinierten Steuerelementen mit hoher Leistung.  In den meisten Fällen bieten die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Frameworkobjekte auf höherer Ebene, z. B. <xref:System.Windows.Controls.Canvas> und <xref:System.Windows.Controls.TextBlock>, größere Flexibilität und Bedienungsfreundlichkeit.  
  
### Treffertests  
 Die <xref:System.Windows.Media.VisualTreeHelper>\-Klasse bietet Methoden für Treffertests für visuelle Objekte, wenn die standardmäßige Unterstützung für Treffertests nicht Ihren Anforderungen entspricht.  Sie können mit den <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>\-Methoden in der <xref:System.Windows.Media.VisualTreeHelper>\-Klasse bestimmen, ob eine Geometrie oder ein Punktkoordinatenwert sich innerhalb der Begrenzung eines bestimmten Objekts, z. B. eines Steuerelements oder eines grafischen Elements, befindet.  Sie könnten z. B. mit Treffertests bestimmen, ob ein Mausklick innerhalb des umgebenden Rechtecks eines Objekts in die Geometrie eines Kreises fällt. Sie haben auch die Möglichkeit, die Standardimplementierung der Treffertests zu überschreiben, um eigene benutzerdefinierte Treffertestberechnungen durchzuführen.  
  
 Weitere Informationen zu Treffertests finden Sie unter [Treffertests in der visuellen Ebene](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
### Auflisten der visuellen Struktur  
 Die <xref:System.Windows.Media.VisualTreeHelper>\-Klasse stellt Funktionalität zum Auflisten der Member einer visuellen Struktur bereit.  Zum Abrufen eines übergeordneten Elements rufen Sie die <xref:System.Windows.Media.VisualTreeHelper.GetParent%2A>\-Methode auf.  Um ein untergeordnetes Element oder ein in der Hierarchie unmittelbares Nachfolgerelement eines visuellen Objekts abzurufen, rufen Sie die <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A>\-Methode auf.  Diese Methode gibt ein untergeordnetes <xref:System.Windows.Media.Visual> des übergeordneten Elements am angegebenen Index zurück.  
  
 Im folgenden Beispiel wird gezeigt, wie alle Nachfolgerelemente eines visuellen Objekts aufgelistet werden. Dieses Verfahren können Sie verwenden, wenn Sie alle Renderinginformationen einer Hierarchie visueller Objekte serialisieren möchten.  
  
 [!code-csharp[VisualsOverview#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#101)]
 [!code-vb[VisualsOverview#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#101)]  
  
 In den meisten Fällen ist die logische Struktur eine hilfreichere Darstellung der Elemente in einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung.  Auch wenn Sie die logische Struktur nicht direkt ändern, ist diese Ansicht der Anwendung hilfreich, um Eigenschaftenvererbung und Ereignisrouting zu verstehen.  Im Gegensatz zur visuellen Struktur kann die logische Struktur nicht visuelle Datenobjekte, z. B. <xref:System.Windows.Documents.ListItem>, darstellen.  Weitere Informationen über die logische Struktur finden Sie unter [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
 Die <xref:System.Windows.Media.VisualTreeHelper>\-Klasse stellt Methoden zum Zurückgeben des umgebenden Rechtecks visueller Objekte bereit.  Sie können das umgebende Rechteck eines visuellen Objekts durch Aufrufen von <xref:System.Windows.Media.VisualTreeHelper.GetContentBounds%2A> zurückgeben.  Das umgebende Rechteck aller Nachfolgerelemente eines visuellen Objekts, einschließlich des visuellen Objekts selbst, können Sie durch Aufrufen von <xref:System.Windows.Media.VisualTreeHelper.GetDescendantBounds%2A> zurückgeben.  Im folgenden Code wird gezeigt, wie das umgebende Rechteck eines visuellen Objekts und all seiner Nachfolgerelemente in der Hierarchie berechnet wird.  
  
 [!code-csharp[VisualsOverview#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#102)]
 [!code-vb[VisualsOverview#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#102)]  
  
## Siehe auch  
 <xref:System.Windows.Media.Visual>   
 <xref:System.Windows.Media.VisualTreeHelper>   
 <xref:System.Windows.Media.DrawingVisual>   
 [2D\-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Treffertests in der visuellen Ebene](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)   
 [Verwenden von DrawingVisual\-Objekten](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)   
 [Lernprogramm: Hosten von visuellen Objekten in einer Win32\-Anwendung](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)   
 [Optimieren der WPF\-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)