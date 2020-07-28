---
title: Übersicht über Adorner
description: Erfahren Sie mehr über Windows Presentation Foundation Adorner, eine besondere Art von FrameworkElement, das Hinweise für einen Benutzer bereitstellt, z. b. funktionale Handles für Elemente.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: 43d4af9f86c6ae72a61f86d1ca19405c2dcc6cc8
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167732"
---
# <a name="adorners-overview"></a>Übersicht über Adorner

Adorner sind ein spezieller Typ von <xref:System.Windows.FrameworkElement> , der verwendet wird, um einem Benutzer visuelle Hinweise bereitzustellen. Adorner können unter anderem verwendet werden, um Elementen funktionale Ziehpunkte hinzuzufügen oder Zustandsinformationen über Steuerelemente bereitzustellen.

## <a name="about-adorners"></a>Informationen über Adorner

Ein <xref:System.Windows.Documents.Adorner> ist ein benutzerdefiniertes <xref:System.Windows.FrameworkElement> , das an einen gebunden ist <xref:System.Windows.UIElement> . Adorner werden in einer gerendert <xref:System.Windows.Documents.AdornerLayer> , bei der es sich um eine Renderingoberfläche handelt, die immer oberhalb des verzierten Elements oder einer Auflistung von geschmückten Elementen liegt. Das Rendering eines Adorners ist unabhängig vom Rendering von <xref:System.Windows.UIElement> , an das der Funktions Indikator gebunden ist. Ein Funktions Indikator wird in der Regel relativ zu dem Element positioniert, an das es gebunden ist. dabei wird der standardmäßige 2D-Koordinaten Ursprung verwendet, der sich in der linken oberen Ecke des verzierten Elements befindet.

Adorner finden eine breite Anwendung in folgenden Fällen:

- Hinzufügen von funktionalen Handles zu einem <xref:System.Windows.UIElement> , mit dem ein Benutzer das Element auf irgendeine Weise bearbeiten kann (Größe ändern, drehen, neu positionieren usw.).
- Bereitstellen von visuellem Feedback, um verschiedene Zustände anzugeben oder auf verschiedene Ereignisse zu reagieren.
- Überlagern visueller Dekorationen auf einem <xref:System.Windows.UIElement> .
- Visuelles maskieren oder außer Kraft setzen eines Teils oder aller <xref:System.Windows.UIElement> .

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt ein grundlegendes Framework zum Verzieren von visuellen Elementen bereit. In der folgenden Tabelle sind die zum Verzieren von Objekten verwendeten primären Typen samt deren Zweck aufgelistet. Es folgen einige Beispiele für die Verwendung:

|||
|-|-|
|<xref:System.Windows.Documents.Adorner>|Eine abstrakte Basisklasse, von der alle einzelnen Adornerimplementierungen geerbt werden.|
|<xref:System.Windows.Documents.AdornerLayer>|Eine Klasse, die eine Rendering-Ebene für den (die) Adorner eines oder mehrerer verzierten Elementen darstellt.|
|<xref:System.Windows.Documents.AdornerDecorator>|Eine Klasse, mit der eine Adorner-Ebene einer Auflistung von Elementen zugeordnet werden kann.|

## <a name="implementing-a-custom-adorner"></a>Implementierung eines benutzerdefinierten Adorners

Das von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bereitgestellte Adorner-Framework dient in erster Linie der Unterstützung beim Erstellen benutzerdefinierter Adorner. Ein benutzerdefinierter Funktions Indikator wird erstellt, indem eine Klasse implementiert wird, die von der abstrakten-Klasse erbt <xref:System.Windows.Documents.Adorner> .

> [!NOTE]
> Das übergeordnete <xref:System.Windows.Documents.Adorner> Element eines ist das, das <xref:System.Windows.Documents.AdornerLayer> den rendert <xref:System.Windows.Documents.Adorner> , nicht das Element, das verziert wird.

Im folgenden Beispiel wird eine Klasse dargestellt, in der ein einfacher Adorner implementiert wird. Der Beispiel Funktions Indikator zeigt einfach die Ecken eines <xref:System.Windows.UIElement> mit Kreisen an.

[!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
[!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]
  
Die folgende Abbildung zeigt den SimpleCircleAdorner, der auf einen angewendet wird <xref:System.Windows.Controls.TextBox> :

![Screenshot, der ein geschmucktes Textfeld anzeigt.](./media/adorners-overview/simplecircleadorner-textbox.png)

## <a name="rendering-behavior-for-adorners"></a>Renderingverhalten der Adorner

Beachten Sie, dass für Adorner kein Renderingverhalten festgelegt ist. Damit wird sichergestellt, dass für das Rendering die Adorner-Implementierung verantwortlich ist. Eine gängige Methode zum Implementieren des Renderingverhaltens ist das Überschreiben der <xref:System.Windows.UIElement.OnRender%2A> -Methode und das Verwenden eines oder mehrerer <xref:System.Windows.Media.DrawingContext> -Objekte, um die visuellen Elemente des Adorners nach Bedarf zu rendern (wie im obigen Beispiel gezeigt).

> [!NOTE]
> Sämtliche Elemente auf der Adorner-Ebene werden vor allen anderen Stilen gerendert, die Sie festgelegt haben. Anders gesagt, befinden sich Adorner visuell stets im Vordergrund und können in der Z-Reihenfolge nicht überschrieben werden.

## <a name="events-and-hit-testing"></a>Ereignisse und Treffertests

Adorner empfangen Eingabeereignisse wie jede andere <xref:System.Windows.FrameworkElement> .  Da ein Funktions Indikator immer eine höhere z-Reihenfolge als das Element hat, das er als Zusatzelement dient, empfängt der Funktions Indikator Eingabeereignisse (z. b. <xref:System.Windows.UIElement.Drop> oder <xref:System.Windows.UIElement.MouseMove> ), die für das zugrunde liegende verzierte Element bestimmt sein können.  Ein Adorner kann bestimmte Eingabeereignisse überwachen und diese durch erneutes Auslösen des Ereignisses an das zugrunde liegende verzierte Element weiterleiten.

Um Pass-Through-Treffer Tests von Elementen unter einem Adorner zu aktivieren, legen Sie die Eigenschaft Treffer Test für <xref:System.Windows.UIElement.IsHitTestVisible%2A> den Adorner auf **false** fest.  Weitere Informationen zu Treffer Tests finden Sie unter [Treffer Tests in der visuellen Ebene](../graphics-multimedia/hit-testing-in-the-visual-layer.md).

## <a name="adorning-a-single-uielement"></a>Verzieren eines einzelnen UIElement-Elements

Führen Sie die folgenden Schritte aus, um einen Funktions Indikator an einen bestimmten zu binden <xref:System.Windows.UIElement> :

1. Ruft die statische-Methode <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> auf, um ein-Objekt zu erhalten, <xref:System.Windows.Documents.AdornerLayer> das <xref:System.Windows.UIElement> zu schmücken ist. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>durchläuft die visuelle Struktur, beginnend beim angegebenen <xref:System.Windows.UIElement> und gibt die erste gefundene Adornerebene zurück. (Falls keine Adorner-Ebenen gefunden werden, gibt die Methode NULL zurück.)

2. Ruft die- <xref:System.Windows.Documents.AdornerLayer.Add%2A> Methode auf, um den Funktions Indikator an das Ziel zu binden <xref:System.Windows.UIElement> .

 Im folgenden Beispiel wird ein SimpleCircleAdorner (siehe oben) an ein <xref:System.Windows.Controls.TextBox> benanntes *MyTextBox*-Element gebunden:

 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]

> [!NOTE]
> Das Binden von Adornern an andere Elemente mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird derzeit nicht unterstützt.

## <a name="adorning-the-children-of-a-panel"></a>Verzieren der untergeordneten Elemente eines Panels

Führen Sie die folgenden Schritte aus, um einen Funktions Indikator an die untergeordneten Elemente eines zu binden <xref:System.Windows.Controls.Panel> :

1. Ruft die- `static` Methode <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> auf, um eine Adornerebene für das Element zu finden, dessen untergeordnete Elemente geschmückt werden sollen.

2. Listet die untergeordneten Elemente des übergeordneten Elements auf und ruft die- <xref:System.Windows.Documents.AdornerLayer.Add%2A> Methode auf, um einen Funktions Indikator an jedes untergeordnete Element zu binden.

Im folgenden Beispiel wird ein SimpleCircleAdorner (siehe oben) an die untergeordneten Elemente eines <xref:System.Windows.Controls.StackPanel> benannten *myStackPanel*-Steuer Elements gebunden:

[!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
[!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.AdornerHitTestResult>
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [Übersicht über Zeichnungsobjekte](../graphics-multimedia/drawing-objects-overview.md)
- [Artikel zu Vorgehensweisen](adorners-how-to-topics.md)
