---
title: "Layout | Microsoft Docs"
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
  - "Steuerelemente [WPF], Layoutsystem"
  - "Layoutsystem [WPF]"
  - "WPF-Layoutsystem"
ms.assetid: 3eecdced-3623-403a-a077-7595453a9221
caps.latest.revision: 31
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# Layout
In diesem Thema wird das [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Layoutsystem beschrieben.  Das Verständnis dazu, wie und wann Layoutberechnungen auftreten, ist von grundlegender Bedeutung für das Erstellen von Benutzeroberflächen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Umgebende Felder für Elemente](#LayoutSystem_BoundingBox)  
  
-   [Das Layoutsystem](#LayoutSystem_Overview)  
  
-   [Messen und Anordnen von untergeordneten Elementen](#LayoutSystem_Measure_Arrange)  
  
-   [Panel\-Elemente und benutzerdefiniertes Layoutverhalten](#LayoutSystem_PanelsCustom)  
  
-   [Überlegungen zur Leistungsfähigkeit des Layouts](#LayoutSystem_Performance)  
  
-   [Teilpixelrendering und Layoutrundung](#LayoutSystem_LayoutRounding)  
  
-   [Weitere Informationen](#LayoutSystem_whatsnext)  
  
<a name="LayoutSystem_BoundingBox"></a>   
## Umgebende Felder für Elemente  
 Wenn Sie ein Layout in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erstellen möchten, ist es wichtig, dass Sie Kenntnisse über das umgebende Feld haben, das alle Elemente umgibt.  Jedes vom Layoutsystem verwendete <xref:System.Windows.FrameworkElement> kann als Rechteck gesehen werden, das in das Layout eingefügt wird.  Die<xref:System.Windows.Controls.Primitives.LayoutInformation>\-Klasse gibt die Grenzen der Layoutzuordnung eines Elements oder einen Slot zurück.  Die Größe des Rechtecks wird festgelegt, indem der verfügbare Bildschirmplatz, die Größe eventuell vorhandener Einschränkungen, Layout\-spezifische Eigenschaften wie Margin und Padding sowie das individuelle Verhalten des übergeordneten <xref:System.Windows.Controls.Panel>\-Elements berechnet werden.  Durch Verarbeitung dieser Daten ist das Layoutsystem in der Lage, die Position aller untergeordneten Elemente für ein bestimmtes <xref:System.Windows.Controls.Panel> zu berechnen.  Sie sollten berücksichtigen, dass die auf dem übergeordneten Element definierten Größenanpassungsmerkmale \(wie z. B. <xref:System.Windows.Controls.Border>\) die untergeordneten Elemente beeinflussen.  
  
 Die folgende Abbildung veranschaulicht ein einfaches Layout.  
  
 ![Ein typisches Raster, ohne überlagerndes umgebendes Feld.](../../../../docs/framework/wpf/advanced/media/boundingbox1.png "boundingbox1")  
  
 Dieses Layout kann mit dem folgenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Code erstellt werden.  
  
 [!code-xml[LayoutInformation#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml#1)]  
  
 Ein einzelnes <xref:System.Windows.Controls.TextBlock>\-Element wird innerhalb eines <xref:System.Windows.Controls.Grid> gehostet.  Während der Text nur die linke obere Ecke der ersten Spalte ausfüllt, ist der reservierte Platz für den <xref:System.Windows.Controls.TextBlock> eigentlich viel größer.  Das umgebende Feld für ein <xref:System.Windows.FrameworkElement> kann mit der <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A>\-Methode abgerufen werden.  Die folgende Abbildung stellt das umgebende Feld für das <xref:System.Windows.Controls.TextBlock>\-Element dar.  
  
 ![Das umgebende Feld des TextBlocks ist jetzt sichtbar.](../../../../docs/framework/wpf/advanced/media/boundingbox2.png "boundingbox2")  
  
 Wie durch das gelbe Rechteck angezeigt, ist der reservierte Platz für das <xref:System.Windows.Controls.TextBlock>\-Element tatsächlich viel größer als angezeigt.  Wenn dem <xref:System.Windows.Controls.Grid> zusätzliche Elemente hinzugefügt werden, könnte diese Zuordnung abhängig von dem Typ und der Größe der hinzugefügten Elemente kleiner oder größer werden.  
  
 Der Layoutplatz des <xref:System.Windows.Controls.TextBlock> wird mit der <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A>\-Methode in einen <xref:System.Windows.Shapes.Path> übersetzt.  Diese Technik kann hilfreich sein, um das umgebende Feld eines Elements anzuzeigen.  
  
 [!code-csharp[LayoutInformation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml.cs#2)]
 [!code-vb[LayoutInformation#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LayoutInformation/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="LayoutSystem_Overview"></a>   
## Das Layoutsystem  
 Im einfachsten Fall ist das Layout ein rekursives System, das dafür sorgt, dass die Größe eines Elements angepasst, das Element positioniert und gezeichnet wird.  Im Detail beschreibt das Layout den Prozess zum Messen und Anordnen der Member einer <xref:System.Windows.Controls.Panel.Children%2A>\-Auflistung eines <xref:System.Windows.Controls.Panel>\-Elements.  Layout ist ein intensiver Prozess.  Je größer die <xref:System.Windows.Controls.Panel.Children%2A>\-Auflistung, desto größer die Anzahl der Berechnungen, die vorgenommen werden müssen.  Auch das Layoutverhalten, das vom <xref:System.Windows.Controls.Panel>\-Element \(dem Besitzer der Auflistung\) definiert wird, kann zu höherer Komplexität führen.  Ein relativ einfacher <xref:System.Windows.Controls.Panel>, z. B. <xref:System.Windows.Controls.Canvas>, kann eine bedeutend bessere Leistung aufweisen als ein komplexerer <xref:System.Windows.Controls.Panel>, z. B. <xref:System.Windows.Controls.Grid>.  
  
 Jedes Mal, wenn ein untergeordnetes <xref:System.Windows.UIElement> seine Position ändert, kann ein neuer Durchlauf des Layoutsystems ausgelöst werden.  Sie sollten wissen, durch welche Ereignisse das Layoutsystem aufgerufen werden kann, da unnötige Aufrufe die Leistung der Anwendung verschlechtern können.  Im Folgenden wird der Prozess beschrieben, der ausgeführt wird, wenn das Layoutsystem aufgerufen wird.  
  
1.  Ein untergeordnetes <xref:System.Windows.UIElement> startet den Layoutprozess, indem es zunächst seine Kerneigenschaften messen lässt.  
  
2.  Die in <xref:System.Windows.FrameworkElement> definierten Größeneigenschaften werden ausgewertet, z. B. <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Margin%2A>.  
  
3.  Die für das <xref:System.Windows.Controls.Panel>\-Element spezifische Logik wird angewendet, z. B. die <xref:System.Windows.Controls.Dock>\-Richtung oder die Stapel\-<xref:System.Windows.Controls.StackPanel.Orientation%2A>.  
  
4.  Der Inhalt wird angeordnet, nachdem alle untergeordneten Elemente gemessen wurden.  
  
5.  Die <xref:System.Windows.Controls.Panel.Children%2A>\-Auflistung wird auf dem Bildschirm gezeichnet.  
  
6.  Der Prozess wird erneut aufgerufen, wenn der Auflistung zusätzliche <xref:System.Windows.Controls.Panel.Children%2A> hinzugefügt werden, eine <xref:System.Windows.FrameworkElement.LayoutTransform%2A> angewendet oder die <xref:System.Windows.UIElement.UpdateLayout%2A>\-Methode aufgerufen wird.  
  
 Dieser Prozess und die Vorgehensweise zum Aufrufen des Prozesses wird in den folgenden Abschnitten ausführlich erläutert.  
  
<a name="LayoutSystem_Measure_Arrange"></a>   
## Messen und Anordnen von untergeordneten Elementen  
 Das Layoutsystem führt für jedes Member der untergeordneten <xref:System.Windows.Controls.Panel.Children%2A>\-Auflistung zwei Durchläufe durch: eine Maßübergabe und eine Anordnungsübergabe.  Jedes untergeordnete <xref:System.Windows.Controls.Panel>\-Element bietet eine eigene <xref:System.Windows.FrameworkElement.MeasureOverride%2A>\-Methode und <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>\-Methode für das eigene spezifische Layoutverhalten.  
  
 Während der Maßübergabe wird jedes Member der <xref:System.Windows.Controls.Panel.Children%2A>\-Auflistung ausgewertet.  Der Prozess beginnt mit einem Aufruf an die <xref:System.Windows.UIElement.Measure%2A>\-Methode.  Diese Methode wird innerhalb der Implementierung des übergeordneten <xref:System.Windows.Controls.Panel>\-Elements aufgerufen. Sie muss nicht explizit aufgerufen werden, um das Layout durchzuführen.  
  
 Zuerst werden systemeigene Größeneigenschaften für das <xref:System.Windows.UIElement> ausgewertet, z. B. <xref:System.Windows.UIElement.Clip%2A> und <xref:System.Windows.UIElement.Visibility%2A>.  Dies generiert einen Wert mit der Bezeichnung `constraintSize`, der an <xref:System.Windows.FrameworkElement.MeasureCore%2A> übergeben wird.  
  
 Danach werden auf <xref:System.Windows.FrameworkElement> definierte Frameworkeigenschaften verarbeitet, was sich auf den Wert von `constraintSize` auswirkt.  Diese Eigenschaften beschreiben normalerweise die Größenanpassungsmerkmale für das zugrunde liegende <xref:System.Windows.UIElement>, z. B. <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> und <xref:System.Windows.FrameworkElement.Style%2A>.  Jede dieser Eigenschaften kann den Raum ändern, der zur Anzeige des Elements erforderlich ist.  <xref:System.Windows.FrameworkElement.MeasureOverride%2A> wird dann mit `constraintSize` als Parameter aufgerufen.  
  
> [!NOTE]
>  Es gibt einen Unterschied zwischen den Eigenschaften von <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.ActualHeight%2A> und <xref:System.Windows.FrameworkElement.ActualWidth%2A>.  Die <xref:System.Windows.FrameworkElement.ActualHeight%2A>\-Eigenschaft ist beispielsweise ein berechneter Wert, der auf anderen Höheneingaben und dem Layoutsystem beruht.  Der Wert wird von dem Layoutsystem selbst auf Grundlage des tatsächlichen Renderingdurchlaufs festgelegt und kann aus diesem Grund etwas kleiner sein als der Wert, der für Eigenschaften festgelegt wird, welche die Grundlage für die Eingabeänderung sind, wie z. B. <xref:System.Windows.FrameworkElement.Height%2A>.  
>   
>  Da es sich bei <xref:System.Windows.FrameworkElement.ActualHeight%2A> um einen berechneten Wert handelt, sollten Sie daran denken, dass es mehrere oder inkrementelle gemeldete Änderungen dieses Werts geben kann, die das Ergebnis verschiedener Vorgänge des Layoutsystems sind.  Unter Umständen meldet das Layoutsystem den erforderlichen Platz für untergeordnete Elemente, Einschränkungen durch das übergeordnete Element usw.  
  
 Das Ziel der Maßübergabe ist letztendlich, dass das untergeordnete Element seine <xref:System.Windows.UIElement.DesiredSize%2A> festlegt. Dies geschieht während des <xref:System.Windows.FrameworkElement.MeasureCore%2A>\-Aufrufs.  Der <xref:System.Windows.UIElement.DesiredSize%2A>\-Wert wird von <xref:System.Windows.UIElement.Measure%2A> zur Verwendung während der Anordungsübergabe für den Inhalt gespeichert.  
  
 Die Anordnungsübergabe beginnt mit einem Aufruf an die <xref:System.Windows.UIElement.Arrange%2A>\-Methode.  Während der Anordnungsübergabe generiert das übergeordnete <xref:System.Windows.Controls.Panel>\-Element ein Rechteck, das die Grenzen des untergeordneten Elements darstellt.  Dieser Wert wird zur Verarbeitung an die <xref:System.Windows.FrameworkElement.ArrangeCore%2A>\-Methode übergeben.  
  
 Die <xref:System.Windows.FrameworkElement.ArrangeCore%2A>\-Methode wertet den <xref:System.Windows.UIElement.DesiredSize%2A>\-Wert des untergeordneten Elements aus und wertet alle zusätzlichen Ränder aus, die sich möglicherweise auf die gerenderte Größe des Elements auswirken.  <xref:System.Windows.FrameworkElement.ArrangeCore%2A> generiert einen `arrangeSize`, der an die <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>\-Methode des <xref:System.Windows.Controls.Panel> als Parameter übergeben wird.  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> generiert den `finalSize` des untergeordneten Elements.  Schließlich führt die <xref:System.Windows.FrameworkElement.ArrangeCore%2A>\-Methode eine endgültige Auswertung der Offseteigenschaften, wie Rand und Abstand, durch und platziert das untergeordnete Element innerhalb seines Layoutplatzes.  Das untergeordnete Element muss nicht \(und wird häufig nicht\) den gesamten zugeordneten Platz ausfüllen.  Dem übergeordneten <xref:System.Windows.Controls.Panel>\-Element wird dann die Steuerung zurückgegeben, und der Layoutprozess ist abgeschlossen.  
  
<a name="LayoutSystem_PanelsCustom"></a>   
## Panel\-Elemente und benutzerdefiniertes Layoutverhalten  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] schließt eine Gruppe von Elementen ein, die sich von <xref:System.Windows.Controls.Panel> ableiten.  Diese<xref:System.Windows.Controls.Panel>\-Elemente aktivieren viele komplexe Layouts.  Das Stapeln von Elementen kann beispielsweise problemlos durch Verwenden des <xref:System.Windows.Controls.StackPanel>\-Elements erzielt werden, während ein <xref:System.Windows.Controls.Canvas> komplexere, frei fließende Layouts ermöglicht.  
  
 Die folgende Tabelle bietet einen Überblick über die verfügbaren <xref:System.Windows.Controls.Panel>\-Layoutelemente.  
  
|Panel\-Name|Beschreibung|  
|-----------------|------------------|  
|<xref:System.Windows.Controls.Canvas>|Definiert einen Bereich, in dem Sie untergeordnete Elemente explizit mithilfe von Koordinaten positionieren können, die relativ zum <xref:System.Windows.Controls.Canvas>\-Bereich sind.|  
|<xref:System.Windows.Controls.DockPanel>|Definiert einen Bereich, in dem Sie untergeordnete Elemente entweder horizontal oder vertikal relativ zueinander anordnen können.|  
|<xref:System.Windows.Controls.Grid>|Definiert einen flexiblen Rasterbereich, der aus Spalten und Zeilen besteht.|  
|<xref:System.Windows.Controls.StackPanel>|Ordnet untergeordnete Elemente in einer einzelnen Zeile an, die horizontal oder vertikal ausgerichtet sein kann.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|Stellt ein Framework für <xref:System.Windows.Controls.Panel>\-Elemente bereit, die die Auflistung ihrer untergeordneten Daten virtualisieren.  Dies ist eine abstrakte Klasse.|  
|<xref:System.Windows.Controls.WrapPanel>|Positioniert untergeordnete Elemente sequenziell von links nach rechts und umbricht den Inhalt am Rand des enthaltenden Felds auf die nächste Zeile.  Je nach dem Wert der <xref:System.Windows.Controls.WrapPanel.Orientation%2A>\-Eigenschaft erfolgt die weitere Anordnung nacheinander von oben nach unten oder von rechts nach links.|  
  
 Für Anwendungen, die ein Layout erfordern, welches durch Verwendung der vordefinierten <xref:System.Windows.Controls.Panel>\-Elemente nicht erstellt werden kann, können benutzerdefinierte Layoutverhalten erzielt werden, indem Elemente von <xref:System.Windows.Controls.Panel> erben und die <xref:System.Windows.FrameworkElement.MeasureOverride%2A>\-Methode und die <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>\-Methode überschrieben werden.  Ein Beispiel hierfür finden Sie unter [Beispiel für einen benutzerdefinierten radial angeordneten Bereich](http://go.microsoft.com/fwlink/?LinkID=159982).  
  
<a name="LayoutSystem_Performance"></a>   
## Überlegungen zur Leistungsfähigkeit des Layouts  
 Das Layout ist ein rekursiver Prozess.  Bei jedem Aufruf des Layoutystems werden alle untergeordneten Elemente in einer <xref:System.Windows.Controls.Panel.Children%2A>\-Auflistung verarbeitet.  Das Layoutsystem sollte also nur dann ausgelöst werden, wenn es notwendig ist.  Die folgenden Überlegungen können Ihnen helfen, eine bessere Leistung zu erzielen.  
  
-   Beachten Sie, welche Eigenschaftswertänderungen ein rekursives Update durch das Layoutsystem erzwingen.  
  
     Abhängigkeitseigenschaften, deren Werte bewirken können, dass das Layoutsystem initialisiert wird, werden mit öffentlichen Flags markiert.  <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> und <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> stellen nützliche Anhaltspunkte dazu bereit, welche  Eigenschaftswertänderungen ein rekursives Update durch das Layoutsystem erzwingen.  Im Allgemeinen kann jede Eigenschaft, die die Größe des umgebenden Felds eines Elements beeinflussen kann, das <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>\-Flag auf true setzen.  Weitere Informationen finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
-   Verwenden Sie, wenn möglich, einen <xref:System.Windows.UIElement.RenderTransform%2A> statt eines <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.  
  
     <xref:System.Windows.FrameworkElement.LayoutTransform%2A> kann sehr nützlich sein, um den Inhalt einer [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] zu beeinflussen.  Wenn sich der Effekt der Transformation jedoch nicht auf die Position anderer Elemente auswirken muss, empfiehlt es sich, stattdessen einen <xref:System.Windows.UIElement.RenderTransform%2A> zu verwenden, da <xref:System.Windows.UIElement.RenderTransform%2A> das Layoutsystem nicht aufruft.  <xref:System.Windows.FrameworkElement.LayoutTransform%2A> wendet die Transformation an und erzwingt ein rekursives Layoutupdate, um die neue Position des betroffenen Elements zu berücksichtigen.  
  
-   Vermeiden Sie unnötige Aufrufe an <xref:System.Windows.UIElement.UpdateLayout%2A>.  
  
     Die <xref:System.Windows.UIElement.UpdateLayout%2A>\-Methode erzwingt eine rekursive Layoutaktualisierung und ist häufig nicht notwendig.  Wenn Sie nicht sicher sind, ob eine vollständige Aktualisierung notwendig ist, verlassen Sie sich auf das Layoutsystem, das diese Methode für Sie aufruft.  
  
-   Bei einer großen <xref:System.Windows.Controls.Panel.Children%2A>\-Auflistung sollten Sie in Erwägung ziehen, ein <xref:System.Windows.Controls.VirtualizingStackPanel>\-Element anstelle des regulären <xref:System.Windows.Controls.StackPanel>\-Elements zu verwenden.  
  
     Durch das Virtualisieren der Auflistung untergeordneter Elemente behält <xref:System.Windows.Controls.VirtualizingStackPanel> nur die Objekte im Speicher, die sich derzeit im [ViewPort](GTMT) des übergeordneten Elements befinden.  In den meisten Szenarien verbessert dies die Leistung erheblich.  
  
<a name="LayoutSystem_LayoutRounding"></a>   
## Teilpixelrendering und Layoutrundung  
 Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Grafiksystem verwendet geräteunabhängige Einheiten, um Auflösungs\- und Geräteunabhängigkeit zu ermöglichen.  Jedes geräteunabhängige Pixel wird automatisch mit der [!INCLUDE[TLA#tla_dpi](../../../../includes/tlasharptla-dpi-md.md)]\-Einstellung des Systems skaliert.  Dies ermöglicht [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen eine ordnungsgemäße Skalierung für unterschiedliche [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)]\-Einstellungen und bewirkt, dass die Anwendung automatisch [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)]\-Einstellungen berücksichtigt.  
  
 Die [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)]\-Unabhängigkeit kann jedoch zu einem unregelmäßigen Rendern von Rändern aufgrund von Antialiasing führen.  Diese im Allgemeinen als verschwommene oder halbtransparente Ränder wahrgenommenen Artefakte können auftreten, wenn ein Rand in der Mitte eines Gerätepixels und nicht zwischen Gerätepixeln liegt.  Das Layoutsystem bietet eine Möglichkeit, dies mit der Layoutrundung zu korrigieren.  Layoutrundung erfolgt, wenn das Layoutsystem während der Layoutübergabe alle nicht ganzzahligen Pixelwerte rundet.  
  
 Die Layoutrundung ist standardmäßig deaktiviert.  Um die Layoutrundung zu aktivieren, legen Sie die <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>\-Eigenschaft in einem beliebigen <xref:System.Windows.FrameworkElement> auf `true` fest.  Da es sich um eine Abhängigkeitseigenschaft handelt, wird der Wert in der visuellen Struktur an alle untergeordneten Elemente weitergegeben.  Um die Layoutrundung für die gesamte Benutzeroberfläche zu aktivieren, legen Sie <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> im Stammcontainer auf `true` fest.  Ein Beispiel finden Sie unter <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>.  
  
<a name="LayoutSystem_whatsnext"></a>   
## Weitere Informationen  
 Der erste Schritt zum Verständnis des Layouts besteht darin, dass Sie wissen, wie Elemente gemessen und angeordnet werden.  Weitere Informationen über die verfügbaren <xref:System.Windows.Controls.Panel>\-Elemente finden Sie unter [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md).  Informationen zu den verschiedenen Positionierungseigenschaften, die das Layout beeinflussen können, finden Sie unter [Übersicht über Alignment, Margin und Padding](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md).  Ein Beispiel für ein benutzerdefiniertes <xref:System.Windows.Controls.Panel>\-Element finden Sie unter [Beispiel für einen benutzerdefinierten radial angeordneten Bereich](http://go.microsoft.com/fwlink/?LinkID=159982).  Wenn Sie bereit sind, alles in einer Lightweightanwendung zusammenzufügen, lesen Sie [Exemplarische Vorgehensweise: Erste Schritte mit WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## Siehe auch  
 <xref:System.Windows.FrameworkElement>   
 <xref:System.Windows.UIElement>   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Übersicht über Alignment, Margin und Padding](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)   
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)