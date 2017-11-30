---
title: Layout
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
helpviewer_keywords:
- WPF layout system [WPF]
- controls [WPF], layout system
- layout system [WPF]
ms.assetid: 3eecdced-3623-403a-a077-7595453a9221
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 82f5f69390f2b4d27f1f41050971afa9faede960
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="layout"></a>Layout
Dieses Thema beschreibt das Layoutsystem von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Das Verstehen, wie und wann Layoutberechnungen auftreten, ist wichtige für die Erstellung von Benutzeroberflächen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Umgebende Felder für Elemente](#LayoutSystem_BoundingBox)  
  
-   [Das Layoutsystem](#LayoutSystem_Overview)  
  
-   [Messen und Anordnen von untergeordneten Elementen](#LayoutSystem_Measure_Arrange)  
  
-   [Panel-Elemente und benutzerdefiniertes Layoutverhalten](#LayoutSystem_PanelsCustom)  
  
-   [Überlegungen zur Layoutleistung](#LayoutSystem_Performance)  
  
-   [Subpixel-Rendering und Layoutrundung](#LayoutSystem_LayoutRounding)  
  
-   [Weitere Informationen](#LayoutSystem_whatsnext)  
  
<a name="LayoutSystem_BoundingBox"></a>   
## <a name="element-bounding-boxes"></a>Umgebende Felder für Elemente  
 Wenn Sie an das Layout in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] denken, ist es wichtig, die umgebenden Felder zu verstehen, die alle Elemente umschließen. Jede <xref:System.Windows.FrameworkElement> verbraucht durch das Layout System kann betrachtet werden als ein Rechteck, das in das Layout eingefügt wird. Die <xref:System.Windows.Controls.Primitives.LayoutInformation> Klasse gibt die Grenzen der Layout-Zuordnung ein Element bzw. das Einschubfach zurück. Die Größe des Rechtecks richtet sich nach der Berechnung der Bildschirmbereich verfügbar, die Größe der Einschränkungen, Layout-spezifische Eigenschaften (z. B. Rand und Abstand) und die einzelnen Verhalten des übergeordneten Elements <xref:System.Windows.Controls.Panel> Element. Verarbeitung dieser Daten ist das Layoutsystem berechnen, die Position aller untergeordneten Elemente eines bestimmten <xref:System.Windows.Controls.Panel>. Es ist wichtig zu beachten, dass die Größe von Eigenschaften für das übergeordnete Element definiert z. B. eine <xref:System.Windows.Controls.Border>, Einfluss auf die untergeordneten Elemente.  
  
 Die folgende Abbildung zeigt ein einfaches Layout.  
  
 ![Ein typisches Raster, ohne überlagerndes umgebendes Feld.](../../../../docs/framework/wpf/advanced/media/boundingbox1.png "boundingbox1")  
  
 Dieses Layout kann mithilfe der folgenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erreicht werden.  
  
 [!code-xaml[LayoutInformation#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml#1)]  
  
 Ein einzelnes <xref:System.Windows.Controls.TextBlock> Element gehostet wird, innerhalb einer <xref:System.Windows.Controls.Grid>. Während der Text nur die linke obere Ecke der ersten Spalte, für den zugeordneten Platz ausfüllt der <xref:System.Windows.Controls.TextBlock> tatsächlich viel größer ist. Das umgebende Feld eines beliebigen <xref:System.Windows.FrameworkElement> kann abgerufen werden, indem die <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> Methode. Die folgende Abbildung zeigt das umgebende Feld für die <xref:System.Windows.Controls.TextBlock> Element.  
  
 ![Das umgebende Feld des TextBlocks ist jetzt sichtbar.](../../../../docs/framework/wpf/advanced/media/boundingbox2.png "boundingbox2")  
  
 Wie durch das gelbe Rechteck, den zugewiesenen Platz für die <xref:System.Windows.Controls.TextBlock> Element tatsächlich viel größer als angezeigt wird. Wenn zusätzliche Elemente hinzugefügt werden die <xref:System.Windows.Controls.Grid>, Zuordnung verkleinern oder erweitern, je nach Typ und Größe der Elemente, die hinzugefügt werden konnte.  
  
 Der Layout-Slot, der die <xref:System.Windows.Controls.TextBlock> übersetzt in einer <xref:System.Windows.Shapes.Path> mithilfe der <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> Methode. Diese Technik kann für das Anzeigen des umgebenden Felds eines Elements nützlich sein.  
  
 [!code-csharp[LayoutInformation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml.cs#2)]
 [!code-vb[LayoutInformation#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LayoutInformation/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="LayoutSystem_Overview"></a>   
## <a name="the-layout-system"></a>Das Layoutsystem  
 Im einfachsten Fall ist Layout ein rekursives System, um ein Element in der Größe anzupassen, zu positionieren und zu zeichnen. Genauer gesagt, Layout beschreibt den Prozess messen und Anordnen der Member einer <xref:System.Windows.Controls.Panel> des Elements <xref:System.Windows.Controls.Panel.Children%2A> Auflistung. Layout ist ein intensiver Vorgang. Je größer die <xref:System.Windows.Controls.Panel.Children%2A> Auflistung, je größer die Anzahl von Berechnungen, die vorgenommen werden müssen. Komplexität kann auch eingeleitet werden basierend auf dem Layoutverhalten definiert, indem die <xref:System.Windows.Controls.Panel> Element, das die Auflistung besitzt. Ein relativ einfacher <xref:System.Windows.Controls.Panel>, wie z. B. <xref:System.Windows.Controls.Canvas>, können Sie deutlich bessere Leistung als komplexer <xref:System.Windows.Controls.Panel>, wie z. B. <xref:System.Windows.Controls.Grid>.  
  
 Jedes Mal, die ein untergeordnetes Element <xref:System.Windows.UIElement> ändert seine Position, es wurde einen neuen Durchlauf vom Layoutsystem ausgelöst. Daher ist es wichtig, die Ereignisse zu verstehen, die das Layoutsystem aufrufen können, da unnötige Aufrufe zu schlechter Anwendungsleistung führen können. Im Folgenden wird der Prozess beschrieben, der auftritt, wenn das Layoutsystem aufgerufen wird.  
  
1.  Ein untergeordnetes Element <xref:System.Windows.UIElement> zuerst im Layoutprozess zunächst seine Kerneigenschaften gemessen.  
  
2.  Auf definierten Größeneigenschaften <xref:System.Windows.FrameworkElement> ausgewertet werden, z. B. <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, und <xref:System.Windows.FrameworkElement.Margin%2A>.  
  
3.  <xref:System.Windows.Controls.Panel>-spezifische Logik angewendet wird, wie z. B. <xref:System.Windows.Controls.Dock> Richtung oder Stapeln <xref:System.Windows.Controls.StackPanel.Orientation%2A>.  
  
4.  Der Inhalt wird neu angeordnet, nachdem alle untergeordneten Elemente gemessen wurden.  
  
5.  Die <xref:System.Windows.Controls.Panel.Children%2A> Auflistung auf dem Bildschirm gezeichnet wird.  
  
6.  Der Prozess wird erneut aufgerufen, wenn zusätzliche <xref:System.Windows.Controls.Panel.Children%2A> der Auflistung hinzugefügt werden eine <xref:System.Windows.FrameworkElement.LayoutTransform%2A> angewendet wird, oder die <xref:System.Windows.UIElement.UpdateLayout%2A> -Methode aufgerufen wird.  
  
 Dieser Prozess und wie er aufgerufen wird, werden in den folgenden Abschnitten ausführlicher definiert.  
  
<a name="LayoutSystem_Measure_Arrange"></a>   
## <a name="measuring-and-arranging-children"></a>Messen und Anordnen von untergeordneten Elementen  
 Das Layoutsystem führt zwei Durchläufe für jedes Mitglied der <xref:System.Windows.Controls.Panel.Children%2A> Sammlung, übergeben Sie ein Measure und eine anordnungsphase. Jedes untergeordnete Element <xref:System.Windows.Controls.Panel> verfügt über ein eigenes <xref:System.Windows.FrameworkElement.MeasureOverride%2A> und <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Methoden, um einen eigenen bestimmten Layout-Verhalten zu erzielen.  
  
 Während des messdurchgangs jedes Mitglied der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung ausgewertet wird. Der Prozess beginnt mit einem Aufruf der <xref:System.Windows.UIElement.Measure%2A> Methode. Diese Methode wird aufgerufen, in der Implementierung des übergeordneten Elements <xref:System.Windows.Controls.Panel> -Element, und muss nicht explizit aufgerufen werden, für das Layout auftreten.  
  
 Erste, systemeigene Größeneigenschaften des der <xref:System.Windows.UIElement> ausgewertet werden, z. B. <xref:System.Windows.UIElement.Clip%2A> und <xref:System.Windows.UIElement.Visibility%2A>. Dies generiert einen Wert mit dem Namen `constraintSize` übergebene <xref:System.Windows.FrameworkElement.MeasureCore%2A>.  
  
 Zweitens Frameworkeigenschaften, die auf definierten <xref:System.Windows.FrameworkElement> verarbeitet werden, dies wirkt sich auf den Wert des `constraintSize`. Diese Eigenschaften in der Regel beschreiben die Größenanpassungsmerkmale des zugrunde liegenden <xref:System.Windows.UIElement>, z. B. seine <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, und <xref:System.Windows.FrameworkElement.Style%2A>. Jede dieser Eigenschaften kann den Bereich ändern, der zum Anzeigen des Elements nötig ist. <xref:System.Windows.FrameworkElement.MeasureOverride%2A>Klicken Sie dann mit aufgerufen `constraintSize` als Parameter.  
  
> [!NOTE]
>  Es gibt einen Unterschied zwischen den Eigenschaften von <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.ActualHeight%2A> und <xref:System.Windows.FrameworkElement.ActualWidth%2A>. Z. B. die <xref:System.Windows.FrameworkElement.ActualHeight%2A> Eigenschaft ist ein berechneter Wert basierend auf andere Höheneingaben und das Layoutsystem. Der Wert wird vom Layoutsystem selbst, basierend auf einem tatsächlichen Renderingdurchlauf festgelegt und kann daher zurückfallen etwas der festgelegte Wert der Eigenschaften, z. B. <xref:System.Windows.FrameworkElement.Height%2A>, sind die Grundlage für die Eingabe ändern.  
>   
>  Da <xref:System.Windows.FrameworkElement.ActualHeight%2A> wird ein berechneter Wert sollten Sie berücksichtigen, dass es möglicherweise mehrere oder inkrementelle gemeldet ändert, als Ergebnis verschiedener Vorgänge vom Layoutsystem. Das Layoutsystem berechnet möglicherweise den Bereich für untergeordnete Elemente, Einschränkungen durch übergeordnete Elemente usw.  
  
 Das eigentliche Ziel von die Messphase ist für das untergeordnete Element, um zu bestimmen, die <xref:System.Windows.UIElement.DesiredSize%2A>, Dies tritt ein, während die <xref:System.Windows.FrameworkElement.MeasureCore%2A> aufrufen. Die <xref:System.Windows.UIElement.DesiredSize%2A> Wert gespeichert <xref:System.Windows.UIElement.Measure%2A> für die Verwendung während der Inhalt anordnungsphase.  
  
 Die anordnungsphase beginnt mit einem Aufruf von der <xref:System.Windows.UIElement.Arrange%2A> Methode. Während die anordnungsphase der übergeordneten <xref:System.Windows.Controls.Panel> Element erzeugt ein Rechteck, das die Grenzen des untergeordneten Elements darstellt. Dieser Wert wird zum Übergeben der <xref:System.Windows.FrameworkElement.ArrangeCore%2A> Methode für die Verarbeitung.  
  
 Die <xref:System.Windows.FrameworkElement.ArrangeCore%2A> Methode wertet die <xref:System.Windows.UIElement.DesiredSize%2A> des untergeordneten Elements und wertet alle zusätzlichen Ränder, die die gerenderte Größe des Elements beeinflussen können. <xref:System.Windows.FrameworkElement.ArrangeCore%2A>generiert ein `arrangeSize`, der übergeben wird, um die <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Methode der <xref:System.Windows.Controls.Panel> als Parameter. <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>generiert die `finalSize` des untergeordneten Elements. Schließlich die <xref:System.Windows.FrameworkElement.ArrangeCore%2A> Methode führt eine endgültige Auswertung der Offset-Eigenschaften, z. B. Rand und Ausrichtung, durch und platziert das untergeordnete Element innerhalb der Layout-Slot. Das untergeordnete Element muss nicht den gesamten zugewiesenen Bereich füllen (und tut dies häufig auch nicht). Steuerelement dann an das übergeordnete Element zurückgegeben wird <xref:System.Windows.Controls.Panel> und der Layoutvorgang abgeschlossen ist.  
  
<a name="LayoutSystem_PanelsCustom"></a>   
## <a name="panel-elements-and-custom-layout-behaviors"></a>Panel-Elemente und benutzerdefiniertes Layoutverhalten  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]enthält eine Gruppe von Elementen, die davon Herleiten <xref:System.Windows.Controls.Panel>. Diese <xref:System.Windows.Controls.Panel> -Elemente ermöglichen viele komplexe Layouts. Beispielsweise Stapeln Elemente einfach erreichen, indem mithilfe der <xref:System.Windows.Controls.StackPanel> Element, während mit komplexen und kostenlose fließende Layouts möglich sind eine <xref:System.Windows.Controls.Canvas>.  
  
 Die folgende Tabelle enthält die verfügbaren Layouts <xref:System.Windows.Controls.Panel> Elemente.  
  
|Panelname|Beschreibung|  
|----------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Definiert einen Bereich, in dem können Sie explizit untergeordnete Elemente durch Koordinaten relativ zum Positionieren, der <xref:System.Windows.Controls.Canvas> Bereich.|  
|<xref:System.Windows.Controls.DockPanel>|Definiert einen Bereich, in dem Sie untergeordnete Elemente entweder horizontal oder vertikal relativ zueinander anordnen können.|  
|<xref:System.Windows.Controls.Grid>|Definiert einen flexiblen Rasterbereich mit Spalten und Zeilen.|  
|<xref:System.Windows.Controls.StackPanel>|Ordnet untergeordnete Elemente in einer einzelnen Zeile an, die horizontal oder vertikal ausgerichtet werden kann.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|Bietet ein Framework für <xref:System.Windows.Controls.Panel> Elemente, die die Auflistung der untergeordneten Daten virtualisieren. Dies ist eine abstrakte Klasse.|  
|<xref:System.Windows.Controls.WrapPanel>|Ordnet untergeordnete Elemente nacheinander von links nach rechts und umbricht den Inhalt in die nächste Zeile am Rand des enthaltenden Felds. Erfolgt die nachfolgende Sortierung nacheinander von oben nach unten oder von rechts nach links, abhängig vom Wert der <xref:System.Windows.Controls.WrapPanel.Orientation%2A> Eigenschaft.|  
  
 Für Anwendungen, die ein Layout, die nicht möglich ist erfordern mithilfe der vordefinierten <xref:System.Windows.Controls.Panel> Elemente, benutzerdefinierte Layoutverhalten erreichen, indem Sie die Vererbung von <xref:System.Windows.Controls.Panel> und überschreiben die <xref:System.Windows.FrameworkElement.MeasureOverride%2A> und <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Methoden. Ein Beispiel finden Sie unter [Custom Radial Panel Sample (Beispiel des benutzerdefinierten radialen Panels)](http://go.microsoft.com/fwlink/?LinkID=159982).  
  
<a name="LayoutSystem_Performance"></a>   
## <a name="layout-performance-considerations"></a>Überlegungen zur Layoutleistung  
 Layout ist ein rekursiver Prozess. Jedes untergeordnete Element in einem <xref:System.Windows.Controls.Panel.Children%2A> Auflistung bei jedem Aufruf der Layoutsystem verarbeitet wird. Daher sollte das Auslösen des Layoutsystems vermieden werden, wenn es nicht erforderlich ist. Folgendes können Sie für eine bessere Leistung tun.  
  
-   Achten Sie darauf, welche Änderungen des Eigenschaftswerts ein rekursives Update durch das Layoutsystem erzwingt.  
  
     Abhängigkeitseigenschaften, deren Werte bewirken, dass das Layoutsystem initialisiert werden kann, werden mit öffentlichen Flags gekennzeichnet. <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>und <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> nützliche Hinweise, welche Eigenschaft ändert einen rekursiven erzwingt, aktualisieren, indem Sie das Layoutsystem bereitzustellen. Im Allgemeinen müssen eine Eigenschaft, die die Größe des umgebenden Felds eines Elements beeinflussen können eine <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> -flag auf "true" festgelegt. Weitere Informationen finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
-   Verwenden Sie nach Möglichkeit eine <xref:System.Windows.UIElement.RenderTransform%2A> anstelle von einer <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.  
  
     Ein <xref:System.Windows.FrameworkElement.LayoutTransform%2A> kann eine sehr gute Möglichkeit, den Inhalt der Auswirkungen auf eine [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Allerdings verfügt die Auswirkung der Transformation nicht auf die Position von anderen Elementen auswirken, ist es am besten geeignet, eine <xref:System.Windows.UIElement.RenderTransform%2A> stattdessen, da <xref:System.Windows.UIElement.RenderTransform%2A> das Layoutsystem wird nicht aufgerufen. <xref:System.Windows.FrameworkElement.LayoutTransform%2A>Wendet die Transformation, und erzwingt, dass eine rekursive layoutaktualisierung auszuführen, um die neue Position des betroffenen Element zu berücksichtigen.  
  
-   Vermeiden Sie unnötige Aufrufe <xref:System.Windows.UIElement.UpdateLayout%2A>.  
  
     Die <xref:System.Windows.UIElement.UpdateLayout%2A> Methode erzwingt eine rekursive layoutaktualisierung auszuführen, und ist häufig nicht erforderlich. Wenn Sie sicher sind, dass eine vollständige Aktualisierung erforderlich ist, verlassen Sie sich auf das Layoutsystem, das diese Methode für Sie aufruft.  
  
-   Bei der Arbeit mit einer großen <xref:System.Windows.Controls.Panel.Children%2A> -Auflistung, erwägen Sie eine <xref:System.Windows.Controls.VirtualizingStackPanel> statt einer regulären <xref:System.Windows.Controls.StackPanel>.  
  
     Durch die untergeordnete Auflistung virtualisiert die <xref:System.Windows.Controls.VirtualizingStackPanel> behält nur Objekte im Arbeitsspeicher, die zurzeit im ViewPort des übergeordneten Elements enthalten sind. Daher wird die Leistung in den meisten Szenarios erheblich verbessert.  
  
<a name="LayoutSystem_LayoutRounding"></a>   
## <a name="sub-pixel-rendering-and-layout-rounding"></a>Subpixel-Rendering und Layoutglättung  
 Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Grafiksystem verwendet geräteunabhängige Einheiten, um die Unabhängigkeit von der Auflösung und vom Gerät zu aktivieren. Jedes geräteunabhängige Pixel skaliert automatisch mit der [!INCLUDE[TLA#tla_dpi](../../../../includes/tlasharptla-dpi-md.md)]-Einstellung des Systems. Dadurch wird die ordnungsgemäße Skalierung von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen für unterschiedliche [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)]-Einstellungen bereitgestellt, und die Anwendung ist automatisch bereit für [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)].  
  
 Jedoch kann diese [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)]-Unabhängigkeit unregelmäßiges Edge-Rendering aufgrund von Antialiasing hervorrufen. Diese Artefakte, in der Regel verschwommene oder semitransparente Ränder, können auftreten, wenn die Position eines Rands in die Mitte eines Gerätepixels anstatt zwischen die Gerätepixel fällt. Das Layoutsystem bietet eine Möglichkeit, dafür eine Anpassung durch Layoutglättung vorzunehmen. Die Layoutglättung wird verwendet, wo Layoutsysteme nicht-integrale Pixelwerte während des Layoutdurchlaufs glättet.  
  
 Die Layoutglättung ist standardmäßig deaktiviert. Legen Sie zum Aktivieren der layoutglättung der <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> Eigenschaft `true` für ein beliebiges <xref:System.Windows.FrameworkElement>. Da es sich um eine Abhängigkeitseigenschaft handelt, wird der Wert an alle untergeordneten Elemente in der visuellen Struktur weitergegeben. Legen Sie zum Aktivieren der layoutglättung für die gesamte Benutzeroberfläche <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> auf `true` auf den Stammcontainer. Ein Beispiel finden Sie unter <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>.  
  
<a name="LayoutSystem_whatsnext"></a>   
## <a name="whats-next"></a>Weitere Informationen  
 Das Verstehen, wie Elemente gemessen und angeordnet werden, ist der erste Schritt zum Verstehen von Layout. Weitere Informationen zu den verfügbaren <xref:System.Windows.Controls.Panel> Elemente finden Sie unter [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md). Weitere Informationen über die verschiedenen Positionierungseigenschaften, die Layout beeinflussen können, finden Sie unter [Übersicht über Alignment, Margin und Padding](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md). Ein Beispiel eines benutzerdefinierten <xref:System.Windows.Controls.Panel> Element finden Sie unter [benutzerdefinierte radiale Bereichsbeispiel](http://go.microsoft.com/fwlink/?LinkID=159982). Wenn Sie alle in einer Lightweight-Anwendung entwickeln möchten, finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.UIElement>  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Übersicht über Alignment, Margin und Padding](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)  
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)
