---
title: Layout
description: Erfahren Sie, wie und wann Layoutberechnungen im Windows Presentation Foundation Layoutsystem auftreten.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF layout system [WPF]
- controls [WPF], layout system
- layout system [WPF]
ms.assetid: 3eecdced-3623-403a-a077-7595453a9221
ms.openlocfilehash: 0db3f2a6cbabc610362435d64de3fc970f01a73c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164763"
---
# <a name="layout"></a>Layout

In diesem Thema wird das WPF-Layoutsystem (Windows Presentation Foundation) beschrieben. Das Verständnis, wie und wann Layoutberechnungen auftreten, ist wesentlich für das Erstellen von Benutzeroberflächen in WPF.

Dieses Thema enthält folgende Abschnitte:

- [Umgebende Felder für Elemente](#LayoutSystem_BoundingBox)

- [Das Layoutsystem](#LayoutSystem_Overview)

- [Messen und Anordnen von untergeordneten Elementen](#LayoutSystem_Measure_Arrange)

- [Panel-Elemente und benutzerdefiniertes Layoutverhalten](#LayoutSystem_PanelsCustom)

- [Überlegungen zur Layoutleistung](#LayoutSystem_Performance)

- [Subpixel-Rendering und Layoutglättung](#LayoutSystem_LayoutRounding)

- [Was kommt als nächstes](#LayoutSystem_whatsnext)

<a name="LayoutSystem_BoundingBox"></a>

## <a name="element-bounding-boxes"></a>Umgebende Felder für Elemente

Bei der Betrachtung von Layout in WPF ist es wichtig, das umgebende Feld zu verstehen, das alle Elemente umgibt. Jede <xref:System.Windows.FrameworkElement> , die vom Layoutsystem genutzt wird, kann sich als Rechteck vorstellen, das in das Layout geslotet wird. Die <xref:System.Windows.Controls.Primitives.LayoutInformation> -Klasse gibt die Begrenzungen der layoutzuordnung oder des Slots eines Elements zurück. Die Größe des Rechtecks wird durch Berechnen des verfügbaren Bildschirm Raums, der Größe von Einschränkungen, layoutspezifischen Eigenschaften (z. b. Margin und Padding) und des individuellen Verhaltens des übergeordneten <xref:System.Windows.Controls.Panel> Elements ermittelt. Wenn Sie diese Daten verarbeiten, kann das Layoutsystem die Position aller untergeordneten Elemente eines bestimmten berechnen <xref:System.Windows.Controls.Panel> . Beachten Sie, dass sich die für das übergeordnete Element definierten Größen Anpassungs Merkmale, wie z. b. eine, auf die untergeordneten Elemente <xref:System.Windows.Controls.Border> auswirken.

Die folgende Abbildung zeigt ein einfaches Layout.

![Screenshot, der ein typisches Raster zeigt, keine Begrenzungs Felder.](./media/layout/grid-no-bounding-box-superimpose.png)

Dieses Layout kann mithilfe der folgenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erreicht werden.

[!code-xaml[LayoutInformation#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml#1)]

Ein einzelnes- <xref:System.Windows.Controls.TextBlock> Element wird in einem gehostet <xref:System.Windows.Controls.Grid> . Während der Text nur die linke obere Ecke der ersten Spalte füllt, ist der zugeordnete Platz für das <xref:System.Windows.Controls.TextBlock> tatsächlich viel größer. Das umgebende Feld eines beliebigen <xref:System.Windows.FrameworkElement> kann mithilfe der-Methode abgerufen werden <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> . Die folgende Abbildung zeigt das umgebende Feld für das- <xref:System.Windows.Controls.TextBlock> Element.

![Screenshot, der zeigt, dass das TextBlock-Begrenzungsfeld nun sichtbar ist.](./media/layout/visible-textblock-bounding-box.png)

Wie das gelbe Rechteck zeigt, ist der zugeordnete Platz für das- <xref:System.Windows.Controls.TextBlock> Element wesentlich größer als das-Element. Wenn dem weitere Elemente hinzugefügt werden <xref:System.Windows.Controls.Grid> , kann diese Zuordnung je nach Typ und Größe der hinzugefügten Elemente verkleinert oder erweitert werden.

Der Layoutslot von <xref:System.Windows.Controls.TextBlock> wird mithilfe der-Methode in einen übersetzt <xref:System.Windows.Shapes.Path> <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> . Diese Technik kann für das Anzeigen des umgebenden Felds eines Elements nützlich sein.

[!code-csharp[LayoutInformation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml.cs#2)]
[!code-vb[LayoutInformation#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LayoutInformation/VisualBasic/Window1.xaml.vb#2)]

<a name="LayoutSystem_Overview"></a>

## <a name="the-layout-system"></a>Das Layoutsystem

Im einfachsten Fall ist Layout ein rekursives System, um ein Element in der Größe anzupassen, zu positionieren und zu zeichnen. Genauer gesagt beschreibt Layout den Prozess der Messung und Anordnung der Elemente der Auflistung eines <xref:System.Windows.Controls.Panel> Elements <xref:System.Windows.Controls.Panel.Children%2A> . Layout ist ein intensiver Vorgang. Je größer die Auflistung <xref:System.Windows.Controls.Panel.Children%2A> ist, desto größer ist die Anzahl der Berechnungen, die durchgeführt werden müssen. Die Komplexität kann auch basierend auf dem Layoutverhalten eingeführt werden, das durch das Element definiert wird <xref:System.Windows.Controls.Panel> , das die Auflistung besitzt. Eine relativ einfache <xref:System.Windows.Controls.Panel> , z <xref:System.Windows.Controls.Canvas> . b., kann eine deutlich bessere Leistung als eine komplexere Leistung aufweisen <xref:System.Windows.Controls.Panel> , wie z <xref:System.Windows.Controls.Grid> . b..

Jedes Mal, wenn ein <xref:System.Windows.UIElement> untergeordnetes Element seine Position ändert, besteht die Möglichkeit, einen neuen Durchlauf durch das Layoutsystem zu initiieren. Daher ist es wichtig, die Ereignisse zu verstehen, die das Layoutsystem aufrufen können, da unnötige Aufrufe zu schlechter Anwendungsleistung führen können. Im Folgenden wird der Prozess beschrieben, der auftritt, wenn das Layoutsystem aufgerufen wird.

1. Ein untergeordnetes Element <xref:System.Windows.UIElement> beginnt den Layoutprozess, indem zuerst seine Kerneigenschaften gemessen werden.

2. Die für definierten Größen Anpassungs Eigenschaften <xref:System.Windows.FrameworkElement> werden ausgewertet, wie z <xref:System.Windows.FrameworkElement.Width%2A> . b <xref:System.Windows.FrameworkElement.Height%2A> ., und <xref:System.Windows.FrameworkElement.Margin%2A> .

3. <xref:System.Windows.Controls.Panel>-Es wird eine spezifische Logik angewendet, z <xref:System.Windows.Controls.Dock> . b. Richtung oder Stapel <xref:System.Windows.Controls.StackPanel.Orientation%2A> .

4. Der Inhalt wird neu angeordnet, nachdem alle untergeordneten Elemente gemessen wurden.

5. Die Auflistung <xref:System.Windows.Controls.Panel.Children%2A> wird auf dem Bildschirm gezeichnet.

6. Der Prozess wird erneut aufgerufen, wenn <xref:System.Windows.Controls.Panel.Children%2A> der Auflistung weitere hinzugefügt werden, ein <xref:System.Windows.FrameworkElement.LayoutTransform%2A> angewendet wird oder die- <xref:System.Windows.UIElement.UpdateLayout%2A> Methode aufgerufen wird.

Dieser Prozess und wie er aufgerufen wird, werden in den folgenden Abschnitten ausführlicher definiert.

<a name="LayoutSystem_Measure_Arrange"></a>

## <a name="measuring-and-arranging-children"></a>Messen und Anordnen von untergeordneten Elementen

Das Layoutsystem schließt zwei Durchgänge für jedes Element der Auflistung <xref:System.Windows.Controls.Panel.Children%2A> , einen Messdurchlauf und einen Anordnungs Durchlauf ab. Jedes untergeordnete Element <xref:System.Windows.Controls.Panel> stellt seine eigenen <xref:System.Windows.FrameworkElement.MeasureOverride%2A> -und- <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Methoden bereit, um ein eigenes Layoutverhalten zu erzielen.

Während der Maßübergabe wird jeder Member der Auflistung <xref:System.Windows.Controls.Panel.Children%2A> ausgewertet. Der Prozess beginnt mit einem Rückruf der- <xref:System.Windows.UIElement.Measure%2A> Methode. Diese Methode wird innerhalb der-Implementierung des übergeordneten <xref:System.Windows.Controls.Panel> -Elements aufgerufen und muss nicht explizit aufgerufen werden, damit das Layout auftritt.

Zuerst werden die Eigenschaften der systemeigenen Größe von <xref:System.Windows.UIElement> ausgewertet, wie <xref:System.Windows.UIElement.Clip%2A> z <xref:System.Windows.UIElement.Visibility%2A> . b. und. Hierdurch wird ein Wert mit dem Namen generiert `constraintSize` , der an den-Wert <xref:System.Windows.FrameworkElement.MeasureCore%2A>

Zweitens werden Framework-Eigenschaften <xref:System.Windows.FrameworkElement> , die für definiert sind, verarbeitet. Dies wirkt sich auf den Wert von aus `constraintSize` . Diese Eigenschaften beschreiben in der Regel die Größen Anpassungs Merkmale der zugrunde liegenden <xref:System.Windows.UIElement> , wie z <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A> . b.,, <xref:System.Windows.FrameworkElement.Margin%2A> und <xref:System.Windows.FrameworkElement.Style%2A> . Jede dieser Eigenschaften kann den Bereich ändern, der zum Anzeigen des Elements nötig ist. <xref:System.Windows.FrameworkElement.MeasureOverride%2A>wird dann mit `constraintSize` als Parameter aufgerufen.

> [!NOTE]
> Es gibt einen Unterschied zwischen den Eigenschaften von <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A> und und <xref:System.Windows.FrameworkElement.ActualHeight%2A> <xref:System.Windows.FrameworkElement.ActualWidth%2A> . Beispielsweise ist die <xref:System.Windows.FrameworkElement.ActualHeight%2A> -Eigenschaft ein berechneter Wert, der auf anderen Höhen Eingaben und dem Layoutsystem basiert. Der Wert wird vom Layoutsystem selbst festgelegt, basierend auf einem tatsächlichen Renderingdurchlauf, und kann daher etwas hinter dem festgelegten Wert von Eigenschaften, wie z <xref:System.Windows.FrameworkElement.Height%2A> . b., liegen, der die Grundlage für die Eingabe Änderung ist.
>
> Da <xref:System.Windows.FrameworkElement.ActualHeight%2A> ein berechneter Wert ist, sollten Sie beachten, dass es möglicherweise mehrere oder inkrementell gemeldete Änderungen an ihm aufgrund von verschiedenen Vorgängen durch das Layoutsystem gibt. Das Layoutsystem berechnet möglicherweise den Bereich für untergeordnete Elemente, Einschränkungen durch übergeordnete Elemente usw.

Das ultimative Ziel der Measure-Übergabe besteht darin, dass das untergeordnete Element seine <xref:System.Windows.UIElement.DesiredSize%2A> , das während des <xref:System.Windows.FrameworkElement.MeasureCore%2A> Aufrufes eintritt, bestimmt. Der <xref:System.Windows.UIElement.DesiredSize%2A> Wert wird von <xref:System.Windows.UIElement.Measure%2A> zur Verwendung während der Inhalts Anordnungs Übergabe gespeichert.

Der Anordnungs Durchlauf beginnt mit einem Rückruf der- <xref:System.Windows.UIElement.Arrange%2A> Methode. Während der Anordnungs Übergabe generiert das übergeordnete <xref:System.Windows.Controls.Panel> Element ein Rechteck, das die Begrenzungen des untergeordneten Elements darstellt. Dieser Wert wird zur Verarbeitung an die-Methode übermittelt <xref:System.Windows.FrameworkElement.ArrangeCore%2A> .

Die <xref:System.Windows.FrameworkElement.ArrangeCore%2A> -Methode wertet den des untergeordneten <xref:System.Windows.UIElement.DesiredSize%2A> Elements aus und wertet alle zusätzlichen Ränder aus, die sich auf die gerenderte Größe des Elements auswirken können. <xref:System.Windows.FrameworkElement.ArrangeCore%2A>generiert eine `arrangeSize` , die als Parameter an die- <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Methode von übergeben wird <xref:System.Windows.Controls.Panel> . <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>generiert die des untergeordneten-Elements `finalSize` . Schließlich führt die- <xref:System.Windows.FrameworkElement.ArrangeCore%2A> Methode eine abschließende Auswertung der Offset Eigenschaften aus, z. b. "Margin" und "Alignment" und versetzt das untergeordnete Element in den Layoutslot. Das untergeordnete Element muss nicht den gesamten zugewiesenen Bereich füllen (und tut dies häufig auch nicht). Das Steuerelement wird dann an das übergeordnete Element zurückgegeben, <xref:System.Windows.Controls.Panel> und der Layoutprozess ist beendet

<a name="LayoutSystem_PanelsCustom"></a>

## <a name="panel-elements-and-custom-layout-behaviors"></a>Panel-Elemente und benutzerdefiniertes Layoutverhalten

WPF enthält eine Gruppe von Elementen, die von abgeleitet sind <xref:System.Windows.Controls.Panel> . Diese <xref:System.Windows.Controls.Panel> Elemente ermöglichen viele komplexe Layouts. Beispielsweise können Stapel Elemente problemlos mit dem-Element erreicht werden <xref:System.Windows.Controls.StackPanel> , während komplexere und kostenlose fließenden Layouts mithilfe von möglich sind <xref:System.Windows.Controls.Canvas> .

In der folgenden Tabelle sind die verfügbaren <xref:System.Windows.Controls.Panel> Layoutelemente zusammengefasst.

|Panelname|BESCHREIBUNG|
|----------------|-----------------|
|<xref:System.Windows.Controls.Canvas>|Definiert einen Bereich, in dem Sie untergeordnete Elemente explizit durch Koordinaten relativ zum Bereich positionieren können <xref:System.Windows.Controls.Canvas> .|
|<xref:System.Windows.Controls.DockPanel>|Definiert einen Bereich, in dem Sie untergeordnete Elemente entweder horizontal oder vertikal relativ zueinander anordnen können.|
|<xref:System.Windows.Controls.Grid>|Definiert einen flexiblen Rasterbereich mit Spalten und Zeilen.|
|<xref:System.Windows.Controls.StackPanel>|Ordnet untergeordnete Elemente in einer einzelnen Zeile an, die horizontal oder vertikal ausgerichtet werden kann.|
|<xref:System.Windows.Controls.VirtualizingPanel>|Stellt ein Framework für <xref:System.Windows.Controls.Panel>-Elemente bereit, die die Auflistung ihrer untergeordneten Daten virtualisieren. Dies ist eine abstrakte Klasse.|
|<xref:System.Windows.Controls.WrapPanel>|Ordnet untergeordnete Elemente nacheinander von links nach rechts und umbricht den Inhalt in die nächste Zeile am Rand des enthaltenden Felds. Die nachfolgende Reihenfolge erfolgt nacheinander von oben nach unten oder von rechts nach links, abhängig vom Wert der- <xref:System.Windows.Controls.WrapPanel.Orientation%2A> Eigenschaft.|

Bei Anwendungen, für die ein Layout erforderlich ist, das mit einem der vordefinierten Elemente nicht möglich ist <xref:System.Windows.Controls.Panel> , können benutzerdefiniertes Layoutverhalten erreicht werden, indem von geerbt <xref:System.Windows.Controls.Panel> und die <xref:System.Windows.FrameworkElement.MeasureOverride%2A> -und-Methoden überschrieben werden <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> .

<a name="LayoutSystem_Performance"></a>

## <a name="layout-performance-considerations"></a>Überlegungen zur Layoutleistung

Layout ist ein rekursiver Prozess. Jedes untergeordnete Element in einer Auflistung <xref:System.Windows.Controls.Panel.Children%2A> wird bei jedem Aufruf des Layoutsystems verarbeitet. Daher sollte das Auslösen des Layoutsystems vermieden werden, wenn es nicht erforderlich ist. Folgendes können Sie für eine bessere Leistung tun.

- Achten Sie darauf, welche Änderungen des Eigenschaftswerts ein rekursives Update durch das Layoutsystem erzwingt.

  Abhängigkeitseigenschaften, deren Werte bewirken, dass das Layoutsystem initialisiert werden kann, werden mit öffentlichen Flags gekennzeichnet. <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>und <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> geben hilfreiche Hinweise dazu, welche Eigenschafts Wertänderungen ein rekursives Update durch das Layoutsystem erzwingen werden. Im Allgemeinen sollte jede Eigenschaft, die sich auf die Größe des umgebenden Felds eines Elements auswirken kann, über ein <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> Flag verfügen, das auf "true" festgelegt ist. Weitere Informationen finden Sie unter [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md).

- Verwenden Sie nach Möglichkeit einen <xref:System.Windows.UIElement.RenderTransform%2A> anstelle von <xref:System.Windows.FrameworkElement.LayoutTransform%2A> .

  Ein <xref:System.Windows.FrameworkElement.LayoutTransform%2A> kann eine sehr nützliche Möglichkeit sein, den Inhalt eines zu beeinflussen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] . Wenn sich die Auswirkung der Transformation jedoch nicht auf die Position anderer Elemente auswirken muss, empfiehlt es sich, stattdessen einen zu verwenden <xref:System.Windows.UIElement.RenderTransform%2A> , da <xref:System.Windows.UIElement.RenderTransform%2A> das Layoutsystem nicht aufruft. <xref:System.Windows.FrameworkElement.LayoutTransform%2A>wendet die Transformation an und erzwingt eine rekursive layoutaktuaktualisierung, um die neue Position des betroffenen Elements zu berücksichtigen.

- Vermeiden Sie unnötige Aufrufe von <xref:System.Windows.UIElement.UpdateLayout%2A> .

  Die <xref:System.Windows.UIElement.UpdateLayout%2A> -Methode erzwingt eine rekursive layoutaktuaktualisierung und ist häufig nicht erforderlich. Wenn Sie sicher sind, dass eine vollständige Aktualisierung erforderlich ist, verlassen Sie sich auf das Layoutsystem, das diese Methode für Sie aufruft.

- Wenn Sie mit einer großen Auflistung arbeiten, empfiehlt es <xref:System.Windows.Controls.Panel.Children%2A> sich, anstelle eines regulären zu verwenden <xref:System.Windows.Controls.VirtualizingStackPanel> <xref:System.Windows.Controls.StackPanel> .

  Durch die Virtualisierung der untergeordneten Auflistung <xref:System.Windows.Controls.VirtualizingStackPanel> werden von nur Objekte im Arbeitsspeicher gespeichert, die sich derzeit im Viewport des übergeordneten Elements befinden. Daher wird die Leistung in den meisten Szenarios erheblich verbessert.

<a name="LayoutSystem_LayoutRounding"></a>

## <a name="sub-pixel-rendering-and-layout-rounding"></a>Subpixel-Rendering und Layoutglättung

Das WPF-Grafiksystem verwendet geräteunabhängige Einheiten, um Auflösung und Geräteunabhängigkeit zu ermöglichen. Jedes geräteunabhängige Pixel wird automatisch mit der dpi-Einstellung (dots per inch) des Systems skaliert. Dies ermöglicht WPF-Anwendungen die richtige Skalierung für verschiedene DPI-Einstellungen und macht die Anwendung automatisch dpi-fähig.

Diese dpi-Unabhängigkeit kann jedoch ein irreguläres Edge-Rendering aufgrund von Antialiasing erzeugen. Diese Artefakte, in der Regel verschwommene oder semitransparente Ränder, können auftreten, wenn die Position eines Rands in die Mitte eines Gerätepixels anstatt zwischen die Gerätepixel fällt. Das Layoutsystem bietet eine Möglichkeit, dafür eine Anpassung durch Layoutglättung vorzunehmen. Die Layoutglättung wird verwendet, wo Layoutsysteme nicht-integrale Pixelwerte während des Layoutdurchlaufs glättet.

Die Layoutglättung ist standardmäßig deaktiviert. Zum Aktivieren der Layoutrundung legen Sie die- <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> Eigenschaft `true` auf fest <xref:System.Windows.FrameworkElement> . Da es sich um eine Abhängigkeitseigenschaft handelt, wird der Wert an alle untergeordneten Elemente in der visuellen Struktur weitergegeben. Legen Sie für den Stamm Container auf fest, um die Layoutrundung für die gesamte Benutzeroberfläche zu aktivieren <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> `true` . Ein Beispiel finden Sie unter <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>.

<a name="LayoutSystem_whatsnext"></a>

## <a name="whats-next"></a>Nächste Schritte

Das Verstehen, wie Elemente gemessen und angeordnet werden, ist der erste Schritt zum Verstehen von Layout. Weitere Informationen zu den verfügbaren <xref:System.Windows.Controls.Panel> Elementen finden Sie unter [Übersicht über Panels](../controls/panels-overview.md). Weitere Informationen über die verschiedenen Positionierungseigenschaften, die Layout beeinflussen können, finden Sie unter [Übersicht über Alignment, Margin und Padding](alignment-margins-and-padding-overview.md). Wenn Sie bereit sind, alles in einer Lightweight-Anwendung bereitzustellen, finden Sie weitere Informationen unter Exemplarische Vorgehensweise [: meine erste WPF-Desktop Anwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.UIElement>
- [Übersicht über Panel-Elemente](../controls/panels-overview.md)
- [Übersicht über Alignment, Margin und Padding](alignment-margins-and-padding-overview.md)
- [Layout und Entwurf](optimizing-performance-layout-and-design.md)
