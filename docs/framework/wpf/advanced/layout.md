---
title: Layout
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF layout system [WPF]
- controls [WPF], layout system
- layout system [WPF]
ms.assetid: 3eecdced-3623-403a-a077-7595453a9221
ms.openlocfilehash: eb254503f5ce2240a03179da693c66f7ada876be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918295"
---
# <a name="layout"></a>Layout
In diesem Thema wird das WPF-Layoutsystem (Windows Presentation Foundation) beschrieben. Das Verständnis, wie und wann Layoutberechnungen auftreten, ist wesentlich für das Erstellen von Benutzeroberflächen in WPF.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
- [Umgebende Felder für Elemente](#LayoutSystem_BoundingBox)  
  
- [Das Layoutsystem](#LayoutSystem_Overview)  
  
- [Messen und Anordnen von untergeordneten Elementen](#LayoutSystem_Measure_Arrange)  
  
- [Panel-Elemente und benutzerdefiniertes Layoutverhalten](#LayoutSystem_PanelsCustom)  
  
- [Überlegungen zur Layoutleistung](#LayoutSystem_Performance)  
  
- [Subpixel-Rendering und Layoutrundung](#LayoutSystem_LayoutRounding)  
  
- [Weitere Informationen](#LayoutSystem_whatsnext)  
  
<a name="LayoutSystem_BoundingBox"></a>   
## <a name="element-bounding-boxes"></a>Umgebende Felder für Elemente  
 Bei der Betrachtung von Layout in WPF ist es wichtig, das umgebende Feld zu verstehen, das alle Elemente umgibt. Jede <xref:System.Windows.FrameworkElement> , die vom Layoutsystem genutzt wird, kann sich als Rechteck vorstellen, das in das Layout geslotet wird. Die <xref:System.Windows.Controls.Primitives.LayoutInformation> -Klasse gibt die Begrenzungen der layoutzuordnung oder des Slots eines Elements zurück. Die Größe des Rechtecks wird durch Berechnen des verfügbaren Bildschirm Raums, der Größe von Einschränkungen, layoutspezifischen Eigenschaften (z. b. Margin und Padding) und des individuellen Verhaltens des über <xref:System.Windows.Controls.Panel> geordneten Elements ermittelt. Wenn Sie diese Daten verarbeiten, kann das Layoutsystem die Position aller untergeordneten Elemente eines bestimmten <xref:System.Windows.Controls.Panel>berechnen. Beachten Sie, dass sich die für das übergeordnete Element definierten Größen Anpassungs Merkmale, wie <xref:System.Windows.Controls.Border>z. b. eine, auf die untergeordneten Elemente auswirken.  
  
 Die folgende Abbildung zeigt ein einfaches Layout.  
  
 ![Screenshot, der ein typisches Raster zeigt, keine Begrenzungs Felder.](./media/layout/grid-no-bounding-box-superimpose.png)  
  
 Dieses Layout kann mithilfe der folgenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erreicht werden.  
  
 [!code-xaml[LayoutInformation#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml#1)]  
  
 Ein einzelnes <xref:System.Windows.Controls.TextBlock> -Element wird in einem <xref:System.Windows.Controls.Grid>gehostet. Während der Text nur die linke obere Ecke der ersten Spalte füllt, ist der zugeordnete Platz für das <xref:System.Windows.Controls.TextBlock> tatsächlich viel größer. Das umgebende Feld eines beliebigen <xref:System.Windows.FrameworkElement> kann mithilfe der <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> -Methode abgerufen werden. Die folgende Abbildung zeigt das umgebende Feld für das <xref:System.Windows.Controls.TextBlock> -Element.  
  
 ![Screenshot, der zeigt, dass das TextBlock-Begrenzungsfeld nun sichtbar ist.](./media/layout/visible-textblock-bounding-box.png)  
  
 Wie das gelbe Rechteck zeigt, ist der zugeordnete Platz für <xref:System.Windows.Controls.TextBlock> das-Element wesentlich größer als das-Element. Wenn dem <xref:System.Windows.Controls.Grid>weitere Elemente hinzugefügt werden, kann diese Zuordnung je nach Typ und Größe der hinzugefügten Elemente verkleinert oder erweitert werden.  
  
 Der Layoutslot von <xref:System.Windows.Controls.TextBlock> wird mithilfe der <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> - <xref:System.Windows.Shapes.Path> Methode in einen übersetzt. Diese Technik kann für das Anzeigen des umgebenden Felds eines Elements nützlich sein.  
  
 [!code-csharp[LayoutInformation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml.cs#2)]
 [!code-vb[LayoutInformation#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LayoutInformation/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="LayoutSystem_Overview"></a>   
## <a name="the-layout-system"></a>Das Layoutsystem  
 Im einfachsten Fall ist Layout ein rekursives System, um ein Element in der Größe anzupassen, zu positionieren und zu zeichnen. Genauer gesagt beschreibt Layout den Prozess der Messung und Anordnung der <xref:System.Windows.Controls.Panel> <xref:System.Windows.Controls.Panel.Children%2A> Elemente der Auflistung eines Elements. Layout ist ein intensiver Vorgang. Je größer die <xref:System.Windows.Controls.Panel.Children%2A> Auflistung ist, desto größer ist die Anzahl der Berechnungen, die durchgeführt werden müssen. Die Komplexität kann auch basierend auf dem Layoutverhalten eingeführt werden, <xref:System.Windows.Controls.Panel> das durch das Element definiert wird, das die Auflistung besitzt. Eine relativ einfache <xref:System.Windows.Controls.Panel>, <xref:System.Windows.Controls.Canvas>z <xref:System.Windows.Controls.Grid>. b., kann eine deutlich bessere <xref:System.Windows.Controls.Panel>Leistung als eine komplexere Leistung aufweisen, wie z. b.  
  
 Jedes Mal, wenn ein <xref:System.Windows.UIElement> untergeordnetes Element seine Position ändert, besteht die Möglichkeit, einen neuen Durchlauf durch das Layoutsystem zu initiieren. Daher ist es wichtig, die Ereignisse zu verstehen, die das Layoutsystem aufrufen können, da unnötige Aufrufe zu schlechter Anwendungsleistung führen können. Im Folgenden wird der Prozess beschrieben, der auftritt, wenn das Layoutsystem aufgerufen wird.  
  
1. Ein untergeordnetes Element beginntdenLayoutprozess,indemzuerstseineKerneigenschaftengemessenwerden.<xref:System.Windows.UIElement>  
  
2. Die für <xref:System.Windows.FrameworkElement> definierten Größen Anpassungs Eigenschaften werden ausgewertet, <xref:System.Windows.FrameworkElement.Width%2A>wie z. <xref:System.Windows.FrameworkElement.Margin%2A>b., <xref:System.Windows.FrameworkElement.Height%2A>und.  
  
3. <xref:System.Windows.Controls.Panel>-Es wird eine spezifische Logik angewendet, <xref:System.Windows.Controls.Dock> z. b <xref:System.Windows.Controls.StackPanel.Orientation%2A>. Richtung oder Stapel.  
  
4. Der Inhalt wird neu angeordnet, nachdem alle untergeordneten Elemente gemessen wurden.  
  
5. Die <xref:System.Windows.Controls.Panel.Children%2A> Auflistung wird auf dem Bildschirm gezeichnet.  
  
6. Der Prozess wird erneut aufgerufen, wenn <xref:System.Windows.Controls.Panel.Children%2A> der Auflistung weitere hinzugefügt werden, <xref:System.Windows.FrameworkElement.LayoutTransform%2A> ein angewendet wird oder die <xref:System.Windows.UIElement.UpdateLayout%2A> -Methode aufgerufen wird.  
  
 Dieser Prozess und wie er aufgerufen wird, werden in den folgenden Abschnitten ausführlicher definiert.  
  
<a name="LayoutSystem_Measure_Arrange"></a>   
## <a name="measuring-and-arranging-children"></a>Messen und Anordnen von untergeordneten Elementen  
 Das Layoutsystem schließt zwei Durchgänge für jedes Element <xref:System.Windows.Controls.Panel.Children%2A> der Auflistung, einen Messdurchlauf und einen Anordnungs Durchlauf ab. Jedes untergeordnete Element <xref:System.Windows.FrameworkElement.MeasureOverride%2A> <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> stellt seine eigenen-und-Methoden bereit, um ein eigenes Layoutverhalten zu erzielen. <xref:System.Windows.Controls.Panel>  
  
 Während der Maßübergabe wird jeder Member der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung ausgewertet. Der Prozess beginnt mit einem Rückruf der <xref:System.Windows.UIElement.Measure%2A> -Methode. Diese Methode wird innerhalb der-Implementierung des übergeordneten <xref:System.Windows.Controls.Panel> -Elements aufgerufen und muss nicht explizit aufgerufen werden, damit das Layout auftritt.  
  
 Zuerst werden die <xref:System.Windows.UIElement> Eigenschaften der systemeigenen Größe von ausgewertet, <xref:System.Windows.UIElement.Clip%2A> wie z <xref:System.Windows.UIElement.Visibility%2A>. b. und. Hierdurch wird ein Wert `constraintSize` mit dem Namen generiert <xref:System.Windows.FrameworkElement.MeasureCore%2A>, der an den-Wert  
  
 Zweitens werden Framework-Eigenschaften, <xref:System.Windows.FrameworkElement> die für definiert sind, verarbeitet. dies `constraintSize`wirkt sich auf den Wert von aus. Diese Eigenschaften beschreiben in der Regel die Größen Anpassungs Merkmale <xref:System.Windows.UIElement>der zugrunde liegenden, <xref:System.Windows.FrameworkElement.Height%2A>wie <xref:System.Windows.FrameworkElement.Width%2A>z. b <xref:System.Windows.FrameworkElement.Style%2A>.,, <xref:System.Windows.FrameworkElement.Margin%2A>und. Jede dieser Eigenschaften kann den Bereich ändern, der zum Anzeigen des Elements nötig ist. <xref:System.Windows.FrameworkElement.MeasureOverride%2A>wird dann mit `constraintSize` als Parameter aufgerufen.  
  
> [!NOTE]
> Es gibt einen Unterschied zwischen den Eigenschaften <xref:System.Windows.FrameworkElement.Height%2A> von <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.ActualHeight%2A> und <xref:System.Windows.FrameworkElement.ActualWidth%2A>und. Beispielsweise ist die <xref:System.Windows.FrameworkElement.ActualHeight%2A> -Eigenschaft ein berechneter Wert, der auf anderen Höhen Eingaben und dem Layoutsystem basiert. Der Wert wird vom Layoutsystem selbst festgelegt, basierend auf einem tatsächlichen Renderingdurchlauf, und kann daher etwas hinter dem festgelegten Wert von Eigenschaften <xref:System.Windows.FrameworkElement.Height%2A>, wie z. b., liegen, der die Grundlage für die Eingabe Änderung ist.  
>   
>  Da <xref:System.Windows.FrameworkElement.ActualHeight%2A> ein berechneter Wert ist, sollten Sie beachten, dass es möglicherweise mehrere oder inkrementell gemeldete Änderungen an ihm aufgrund von verschiedenen Vorgängen durch das Layoutsystem gibt. Das Layoutsystem berechnet möglicherweise den Bereich für untergeordnete Elemente, Einschränkungen durch übergeordnete Elemente usw.  
  
 Das ultimative Ziel der Measure-Übergabe besteht darin, dass das untergeordnete <xref:System.Windows.UIElement.DesiredSize%2A>Element seine, das während <xref:System.Windows.FrameworkElement.MeasureCore%2A> des Aufrufes eintritt, bestimmt. Der <xref:System.Windows.UIElement.DesiredSize%2A> Wert wird von <xref:System.Windows.UIElement.Measure%2A> zur Verwendung während der Inhalts Anordnungs Übergabe gespeichert.  
  
 Der Anordnungs Durchlauf beginnt mit einem Rückruf der <xref:System.Windows.UIElement.Arrange%2A> -Methode. Während der Anordnungs Übergabe generiert das <xref:System.Windows.Controls.Panel> übergeordnete Element ein Rechteck, das die Begrenzungen des untergeordneten Elements darstellt. Dieser Wert wird zur Verarbeitung an <xref:System.Windows.FrameworkElement.ArrangeCore%2A> die-Methode übermittelt.  
  
 Die <xref:System.Windows.FrameworkElement.ArrangeCore%2A> -Methode wertet <xref:System.Windows.UIElement.DesiredSize%2A> den des untergeordneten Elements aus und wertet alle zusätzlichen Ränder aus, die sich auf die gerenderte Größe des Elements auswirken können. <xref:System.Windows.FrameworkElement.ArrangeCore%2A>generiert eine `arrangeSize`, die <xref:System.Windows.Controls.Panel> als Parameter an die <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> -Methode von übergeben wird. <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>generiert die `finalSize` des untergeordneten-Elements. Schließlich führt die <xref:System.Windows.FrameworkElement.ArrangeCore%2A> -Methode eine abschließende Auswertung der Offset Eigenschaften aus, z. b. "Margin" und "Alignment" und versetzt das untergeordnete Element in den Layoutslot. Das untergeordnete Element muss nicht den gesamten zugewiesenen Bereich füllen (und tut dies häufig auch nicht). Das Steuerelement wird dann an das <xref:System.Windows.Controls.Panel> übergeordnete Element zurückgegeben, und der Layoutprozess ist beendet  
  
<a name="LayoutSystem_PanelsCustom"></a>   
## <a name="panel-elements-and-custom-layout-behaviors"></a>Panel-Elemente und benutzerdefiniertes Layoutverhalten  
WPF enthält eine Gruppe von Elementen, die von <xref:System.Windows.Controls.Panel>abgeleitet sind. Diese <xref:System.Windows.Controls.Panel> Elemente ermöglichen viele komplexe Layouts. Beispielsweise können Stapel Elemente problemlos mit dem <xref:System.Windows.Controls.StackPanel> -Element erreicht werden, während komplexere und kostenlose fließenden Layouts <xref:System.Windows.Controls.Canvas>mithilfe von möglich sind.  
  
 In der folgenden Tabelle sind die Verfüg <xref:System.Windows.Controls.Panel> baren Layoutelemente zusammengefasst.  
  
|Panelname|Beschreibung|  
|----------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Definiert einen Bereich, in dem Sie untergeordnete Elemente explizit durch Koordinaten relativ zum <xref:System.Windows.Controls.Canvas> Bereich positionieren können.|  
|<xref:System.Windows.Controls.DockPanel>|Definiert einen Bereich, in dem Sie untergeordnete Elemente entweder horizontal oder vertikal relativ zueinander anordnen können.|  
|<xref:System.Windows.Controls.Grid>|Definiert einen flexiblen Rasterbereich mit Spalten und Zeilen.|  
|<xref:System.Windows.Controls.StackPanel>|Ordnet untergeordnete Elemente in einer einzelnen Zeile an, die horizontal oder vertikal ausgerichtet werden kann.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|Stellt ein Framework für <xref:System.Windows.Controls.Panel> Elemente bereit, die ihre untergeordnete Datensammlung virtualisieren. Dies ist eine abstrakte Klasse.|  
|<xref:System.Windows.Controls.WrapPanel>|Ordnet untergeordnete Elemente nacheinander von links nach rechts und umbricht den Inhalt in die nächste Zeile am Rand des enthaltenden Felds. Die nachfolgende Reihenfolge erfolgt nacheinander von oben nach unten oder von rechts nach links, abhängig vom Wert <xref:System.Windows.Controls.WrapPanel.Orientation%2A> der-Eigenschaft.|  
  
 Bei Anwendungen, für die ein Layout erforderlich ist, das mit einem <xref:System.Windows.Controls.Panel> der vordefinierten Elemente nicht möglich ist, können benutzerdefiniertes Layoutverhalten erreicht werden, indem von <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> <xref:System.Windows.Controls.Panel> geerbt und die <xref:System.Windows.FrameworkElement.MeasureOverride%2A> -und-Methoden überschrieben werden.  
  
<a name="LayoutSystem_Performance"></a>   
## <a name="layout-performance-considerations"></a>Überlegungen zur Layoutleistung  
 Layout ist ein rekursiver Prozess. Jedes untergeordnete Element in <xref:System.Windows.Controls.Panel.Children%2A> einer Auflistung wird bei jedem Aufruf des Layoutsystems verarbeitet. Daher sollte das Auslösen des Layoutsystems vermieden werden, wenn es nicht erforderlich ist. Folgendes können Sie für eine bessere Leistung tun.  
  
- Achten Sie darauf, welche Änderungen des Eigenschaftswerts ein rekursives Update durch das Layoutsystem erzwingt.  
  
     Abhängigkeitseigenschaften, deren Werte bewirken, dass das Layoutsystem initialisiert werden kann, werden mit öffentlichen Flags gekennzeichnet. <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>und <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> geben hilfreiche Hinweise dazu, welche Eigenschafts Wertänderungen ein rekursives Update durch das Layoutsystem erzwingen werden. Im Allgemeinen sollte jede Eigenschaft, die sich auf die Größe des umgebenden Felds eines Elements auswirken kann, über <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> ein Flag verfügen, das auf "true" festgelegt ist. Weitere Informationen finden Sie unter [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md).  
  
- Verwenden Sie nach Möglichkeit einen <xref:System.Windows.UIElement.RenderTransform%2A> anstelle <xref:System.Windows.FrameworkElement.LayoutTransform%2A>von.  
  
     Ein <xref:System.Windows.FrameworkElement.LayoutTransform%2A> kann eine sehr nützliche Möglichkeit sein, den Inhalt [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]eines zu beeinflussen. Wenn sich die Auswirkung der Transformation jedoch nicht auf die Position anderer Elemente auswirken muss, empfiehlt es sich, stattdessen einen <xref:System.Windows.UIElement.RenderTransform%2A> zu verwenden, da <xref:System.Windows.UIElement.RenderTransform%2A> das Layoutsystem nicht aufruft. <xref:System.Windows.FrameworkElement.LayoutTransform%2A>wendet die Transformation an und erzwingt eine rekursive layoutaktuaktualisierung, um die neue Position des betroffenen Elements zu berücksichtigen.  
  
- Vermeiden Sie unnötige Aufrufe <xref:System.Windows.UIElement.UpdateLayout%2A>von.  
  
     Die <xref:System.Windows.UIElement.UpdateLayout%2A> -Methode erzwingt eine rekursive layoutaktuaktualisierung und ist häufig nicht erforderlich. Wenn Sie sicher sind, dass eine vollständige Aktualisierung erforderlich ist, verlassen Sie sich auf das Layoutsystem, das diese Methode für Sie aufruft.  
  
- Wenn <xref:System.Windows.Controls.Panel.Children%2A> Siemiteinergroßen<xref:System.Windows.Controls.StackPanel>Auflistung arbeiten, empfiehlt es sich, anstelleeinesregulärenzuverwenden.<xref:System.Windows.Controls.VirtualizingStackPanel>  
  
     Durch die Virtualisierung der unter <xref:System.Windows.Controls.VirtualizingStackPanel> geordneten Auflistung werden von nur Objekte im Arbeitsspeicher gespeichert, die sich derzeit im Viewport des übergeordneten Elements befinden. Daher wird die Leistung in den meisten Szenarios erheblich verbessert.  
  
<a name="LayoutSystem_LayoutRounding"></a>   
## <a name="sub-pixel-rendering-and-layout-rounding"></a>Subpixel-Rendering und Layoutglättung  
 Das WPF-Grafiksystem verwendet geräteunabhängige Einheiten, um Auflösung und Geräteunabhängigkeit zu ermöglichen. Jedes geräteunabhängige Pixel wird automatisch mit der dpi-Einstellung (dots per inch) des Systems skaliert. Dies ermöglicht WPF-Anwendungen die richtige Skalierung für verschiedene DPI-Einstellungen und macht die Anwendung automatisch dpi-fähig.  
  
 Diese dpi-Unabhängigkeit kann jedoch ein irreguläres Edge-Rendering aufgrund von Antialiasing erzeugen. Diese Artefakte, in der Regel verschwommene oder semitransparente Ränder, können auftreten, wenn die Position eines Rands in die Mitte eines Gerätepixels anstatt zwischen die Gerätepixel fällt. Das Layoutsystem bietet eine Möglichkeit, dafür eine Anpassung durch Layoutglättung vorzunehmen. Die Layoutglättung wird verwendet, wo Layoutsysteme nicht-integrale Pixelwerte während des Layoutdurchlaufs glättet.  
  
 Die Layoutglättung ist standardmäßig deaktiviert. Zum Aktivieren der Layoutrundung <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> legen Sie `true` die- <xref:System.Windows.FrameworkElement>Eigenschaft auf fest. Da es sich um eine Abhängigkeitseigenschaft handelt, wird der Wert an alle untergeordneten Elemente in der visuellen Struktur weitergegeben. Legen Sie für den Stamm Container auf fest <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> `true` , um die Layoutrundung für die gesamte Benutzeroberfläche zu aktivieren. Ein Beispiel finden Sie unter <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>.  
  
<a name="LayoutSystem_whatsnext"></a>   
## <a name="whats-next"></a>Weitere Informationen  
 Das Verstehen, wie Elemente gemessen und angeordnet werden, ist der erste Schritt zum Verstehen von Layout. Weitere Informationen zu den verfügbaren <xref:System.Windows.Controls.Panel> Elementen finden Sie unter [Übersicht über Panels](../controls/panels-overview.md). Weitere Informationen über die verschiedenen Positionierungseigenschaften, die Layout beeinflussen können, finden Sie unter [Übersicht über Alignment, Margin und Padding](alignment-margins-and-padding-overview.md). Wenn Sie bereit sind, alles in einer Lightweight-Anwendung bereitzustellen, finden [Sie weitere Informationen unter Exemplarische Vorgehensweise: Meine erste WPF-Desktop](../getting-started/walkthrough-my-first-wpf-desktop-application.md)Anwendung.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.UIElement>
- [Übersicht über Panel-Elemente](../controls/panels-overview.md)
- [Übersicht über Alignment, Margin und Padding](alignment-margins-and-padding-overview.md)
- [Layout und Entwurf](optimizing-performance-layout-and-design.md)
