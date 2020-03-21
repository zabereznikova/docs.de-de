---
title: Übersicht über Adorner
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: b41c1f10f7e1b7c1799fd27270a3eeb9899ceeb6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111178"
---
# <a name="adorners-overview"></a>Übersicht über Adorner

Adorner sind eine spezielle <xref:System.Windows.FrameworkElement>Art von , die verwendet wird, um einem Benutzer visuelle Hinweise bereitzustellen. Adorner können unter anderem verwendet werden, um Elementen funktionale Ziehpunkte hinzuzufügen oder Zustandsinformationen über Steuerelemente bereitzustellen.

## <a name="about-adorners"></a>Informationen über Adorner

An <xref:System.Windows.Documents.Adorner> ist <xref:System.Windows.FrameworkElement> ein Benutzer, <xref:System.Windows.UIElement>der an eine gebunden ist. Adorner werden in einer <xref:System.Windows.Documents.AdornerLayer>gerendert, bei der es sich um eine Renderfläche handelt, die sich immer über dem geschmückten Element oder einer Auflistung geschmückter Elemente befindet. Das Rendern eines Adorners <xref:System.Windows.UIElement> ist unabhängig vom Rendern des Adorners, an den der Adorner gebunden ist. Ein Adorner wird in der Regel relativ zu dem Element positioniert, an das er gebunden ist, und verwendet den standardmäßigen 2D-Koordinatenursprung, der sich oben links des geschmückten Elements befindet.

Adorner finden eine breite Anwendung in folgenden Fällen:

- Hinzufügen von funktionalen <xref:System.Windows.UIElement> Handles zu einem, die es einem Benutzer ermöglichen, das Element in irgendeiner Weise zu bearbeiten (Größe ändern, drehen, neu positionieren usw.).
- Bereitstellen von visuellem Feedback, um verschiedene Zustände anzugeben oder auf verschiedene Ereignisse zu reagieren.
- Überlagern Sie visuelle <xref:System.Windows.UIElement>Dekorationen auf einer .
- Visuell maskieren oder überschreiben <xref:System.Windows.UIElement>Sie einen Teil oder den gesamten Teil einer .

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt ein grundlegendes Framework zum Verzieren von visuellen Elementen bereit. In der folgenden Tabelle sind die zum Verzieren von Objekten verwendeten primären Typen samt deren Zweck aufgelistet. Es folgen mehrere Anwendungsbeispiele:

|||
|-|-|
|<xref:System.Windows.Documents.Adorner>|Eine abstrakte Basisklasse, von der alle einzelnen Adornerimplementierungen geerbt werden.|
|<xref:System.Windows.Documents.AdornerLayer>|Eine Klasse, die eine Rendering-Ebene für den (die) Adorner eines oder mehrerer verzierten Elementen darstellt.|
|<xref:System.Windows.Documents.AdornerDecorator>|Eine Klasse, mit der eine Adorner-Ebene einer Auflistung von Elementen zugeordnet werden kann.|

## <a name="implementing-a-custom-adorner"></a>Implementierung eines benutzerdefinierten Adorners

Das von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bereitgestellte Adorner-Framework dient in erster Linie der Unterstützung beim Erstellen benutzerdefinierter Adorner. Ein benutzerdefinierter Adorner wird erstellt, indem eine <xref:System.Windows.Documents.Adorner> Klasse implementiert wird, die von der abstrakten Klasse erbt.

> [!NOTE]
> Das übergeordnete <xref:System.Windows.Documents.Adorner> Element <xref:System.Windows.Documents.AdornerLayer> von an <xref:System.Windows.Documents.Adorner>ist das , das die rendert, nicht das Element, das geschmückt wird.

Im folgenden Beispiel wird eine Klasse dargestellt, in der ein einfacher Adorner implementiert wird. Der Beispieladorner schmückt einfach die <xref:System.Windows.UIElement> Ecken eines mit Kreisen.

[!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
[!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]
  
Das folgende Bild zeigt den SimpleCircleAdorner, der auf eine <xref:System.Windows.Controls.TextBox>angewendet wird:

![Screenshot, der ein geschmücktes Textfeld anzeigt.](./media/adorners-overview/simplecircleadorner-textbox.png)

## <a name="rendering-behavior-for-adorners"></a>Renderingverhalten der Adorner

Beachten Sie, dass für Adorner kein Renderingverhalten festgelegt ist. Damit wird sichergestellt, dass für das Rendering die Adorner-Implementierung verantwortlich ist. Eine gängige Methode zum Implementieren des <xref:System.Windows.UIElement.OnRender%2A> Renderverhaltens besteht darin, die Methode zu überschreiben und ein oder mehrere <xref:System.Windows.Media.DrawingContext> Objekte zu verwenden, um die visuellen Elemente des Adorners nach Bedarf zu rendern (wie im obigen Beispiel gezeigt).

> [!NOTE]
> Sämtliche Elemente auf der Adorner-Ebene werden vor allen anderen Stilen gerendert, die Sie festgelegt haben. Anders gesagt, befinden sich Adorner visuell stets im Vordergrund und können in der Z-Reihenfolge nicht überschrieben werden.

## <a name="events-and-hit-testing"></a>Ereignisse und Treffertests

Adorner empfangen Eingabeereignisse wie <xref:System.Windows.FrameworkElement>alle anderen .  Da ein Adorner immer eine höhere Z-Reihenfolge als das Element aufweist, das <xref:System.Windows.UIElement.Drop> <xref:System.Windows.UIElement.MouseMove>er schmückt, empfängt der Adorner Eingabeereignisse (z. B. oder ), die für das zugrunde liegende geschmückte Element vorgesehen sein können.  Ein Adorner kann bestimmte Eingabeereignisse überwachen und diese durch erneutes Auslösen des Ereignisses an das zugrunde liegende verzierte Element weiterleiten.

Um Pass-Through-Treffertests von Elementen unter einem Adorner zu aktivieren, legen Sie die Treffertesteigenschaft <xref:System.Windows.UIElement.IsHitTestVisible%2A> auf **false** auf dem Adorner fest.  Weitere Informationen zu Treffertests finden Sie unter [Treffertests in der visuellen Ebene](../graphics-multimedia/hit-testing-in-the-visual-layer.md).

## <a name="adorning-a-single-uielement"></a>Verzieren eines einzelnen UIElement-Elements

Führen Sie die folgenden <xref:System.Windows.UIElement>Schritte aus, um einen Adorner an eine bestimmte zu binden:

1. Rufen Sie <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> die statische <xref:System.Windows.Documents.AdornerLayer> Methode <xref:System.Windows.UIElement> auf, um ein Objekt für die zu schmückenden abzurufen. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>führt die visuelle Struktur, beginnend <xref:System.Windows.UIElement>mit der angegebenen , und gibt die erste Adorner-Ebene zurück, die sie findet. (Falls keine Adorner-Ebenen gefunden werden, gibt die Methode NULL zurück.)

2. Rufen <xref:System.Windows.Documents.AdornerLayer.Add%2A> Sie die Methode auf, <xref:System.Windows.UIElement>um den Adorner an das Ziel zu binden.

 Im folgenden Beispiel wird ein SimpleCircleAdorner (siehe oben) an eine <xref:System.Windows.Controls.TextBox> benannte *myTextBox*gebunden:

 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]

> [!NOTE]
> Das Binden von Adornern an andere Elemente mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird derzeit nicht unterstützt.

## <a name="adorning-the-children-of-a-panel"></a>Verzieren der untergeordneten Elemente eines Panels

Führen Sie die folgenden Schritte <xref:System.Windows.Controls.Panel>aus, um einen Adorner an die untergeordneten Elemente eines zu binden:

1. Rufen `static` Sie <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> die Methode auf, um eine Adornerebene für das Element zu finden, dessen untergeordnete Elemente geschmückt werden sollen.

2. Aufzählen durch die untergeordneten Elemente des <xref:System.Windows.Documents.AdornerLayer.Add%2A> übergeordneten Elements, und rufen Sie die Methode auf, um einen Adorner an jedes untergeordnete Element zu binden.

Im folgenden Beispiel wird ein SimpleCircleAdorner (siehe oben) an die untergeordneten Elemente eines <xref:System.Windows.Controls.StackPanel> benannten *myStackPanels*gebunden:

[!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
[!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.AdornerHitTestResult>
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [Übersicht über Zeichnungsobjekte](../graphics-multimedia/drawing-objects-overview.md)
- [How-to-Themen](adorners-how-to-topics.md)
