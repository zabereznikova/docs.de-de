---
title: Übersicht über Adorner
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: d8e6e53edc92a2847c001377706d313cf97cced5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956094"
---
# <a name="adorners-overview"></a>Übersicht über Adorner
Adorner sind ein spezieller Typ von <xref:System.Windows.FrameworkElement>, der verwendet wird, um einem Benutzer visuelle Hinweise bereitzustellen. Adorner können unter anderem verwendet werden, um Elementen funktionale Ziehpunkte hinzuzufügen oder Zustandsinformationen über Steuerelemente bereitzustellen.  

<a name="about_Adorners"></a>   
## <a name="about-adorners"></a>Informationen über Adorner  
 Ein <xref:System.Windows.Documents.Adorner> ist ein Benutzer <xref:System.Windows.FrameworkElement> definiertes, das an <xref:System.Windows.UIElement>einen gebunden ist. Adorner werden in einer <xref:System.Windows.Documents.AdornerLayer>gerendert, bei der es sich um eine Renderingoberfläche handelt, die immer oberhalb des verzierten Elements oder einer Auflistung von geschmückten Elementen liegt. Das Rendering eines Adorners ist unabhängig vom Rendering von <xref:System.Windows.UIElement> , an das der Funktions Indikator gebunden ist. Ein Adorner wird in der Regel relativ zum Element positioniert, an das er gebunden ist. Dazu wird ein 2D-Standardkoordinatenursprung verwendet, der sich in der oberen linken Ecke des verzierten Elements befindet.  
  
 Adorner finden eine breite Anwendung in folgenden Fällen:  
  
- Hinzufügen von funktionalen Handles <xref:System.Windows.UIElement> zu einem, mit dem ein Benutzer das Element auf irgendeine Weise bearbeiten kann (Größe ändern, drehen, neu positionieren usw.).  
  
- Bereitstellen von visuellem Feedback, um verschiedene Zustände anzugeben oder auf verschiedene Ereignisse zu reagieren.  
  
- Überlagern visueller Dekorationen auf <xref:System.Windows.UIElement>einem.  
  
- Visuelles maskieren oder außer Kraft setzen eines Teils <xref:System.Windows.UIElement>oder aller.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt ein grundlegendes Framework zum Verzieren von visuellen Elementen bereit. In der folgenden Tabelle sind die zum Verzieren von Objekten verwendeten primären Typen samt deren Zweck aufgelistet. Es folgen mehrere Verwendungsbeispiele.  
  
|||  
|-|-|  
|<xref:System.Windows.Documents.Adorner>|Eine abstrakte Basisklasse, von der alle einzelnen Adornerimplementierungen geerbt werden.|  
|<xref:System.Windows.Documents.AdornerLayer>|Eine Klasse, die eine Rendering-Ebene für den (die) Adorner eines oder mehrerer verzierten Elementen darstellt.|  
|<xref:System.Windows.Documents.AdornerDecorator>|Eine Klasse, mit der eine Adorner-Ebene einer Auflistung von Elementen zugeordnet werden kann.|  
  
<a name="implement_custom_Adorner"></a>   
## <a name="implementing-a-custom-adorner"></a>Implementierung eines benutzerdefinierten Adorners  
 Das von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bereitgestellte Adorner-Framework dient in erster Linie der Unterstützung beim Erstellen benutzerdefinierter Adorner. Ein benutzerdefinierter Funktions Indikator wird erstellt, indem eine Klasse implementiert wird, die von <xref:System.Windows.Documents.Adorner> der abstrakten-Klasse erbt.  
  
> [!NOTE]
> Das übergeordnete Element <xref:System.Windows.Documents.Adorner> eines ist <xref:System.Windows.Documents.AdornerLayer> das, das <xref:System.Windows.Documents.Adorner>den rendert, nicht das Element, das verziert wird.  
  
 Im folgenden Beispiel wird eine Klasse dargestellt, in der ein einfacher Adorner implementiert wird. Der Beispiel Funktions Indikator zeigt einfach die Ecken eines <xref:System.Windows.UIElement> mit Kreisen an.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
 Die folgende Abbildung zeigt den SimpleCircleAdorner, der auf <xref:System.Windows.Controls.TextBox>ein angewendet wird.  
  
 ![Screenshot, der ein geschmucktes Textfeld anzeigt.](./media/adorners-overview/simplecircleadorner-textbox.png)  
  
<a name="rendering_behavior_for_Adorners"></a>   
## <a name="rendering-behavior-for-adorners"></a>Renderingverhalten der Adorner  
 Beachten Sie, dass für Adorner kein Renderingverhalten festgelegt ist. Damit wird sichergestellt, dass für das Rendering die Adorner-Implementierung verantwortlich ist.   Eine gängige Methode zum Implementieren des Renderingverhaltens ist <xref:System.Windows.UIElement.OnRender%2A> das Überschreiben der-Methode <xref:System.Windows.Media.DrawingContext> und das Verwenden eines oder mehrerer-Objekte, um die visuellen Elemente des Adorners nach Bedarf zu rendern (wie im obigen Beispiel gezeigt).  
  
> [!NOTE]
> Sämtliche Elemente auf der Adorner-Ebene werden vor allen anderen Stilen gerendert, die Sie festgelegt haben. Anders gesagt, befinden sich Adorner visuell stets im Vordergrund und können in der Z-Reihenfolge nicht überschrieben werden.  
  
<a name="adorner_events_hittest"></a>   
## <a name="events-and-hit-testing"></a>Ereignisse und Treffertests  
 Adorner empfangen Eingabeereignisse wie jede andere <xref:System.Windows.FrameworkElement>.  Da ein Funktions Indikator immer eine höhere z-Reihenfolge als das Element hat, das er als Zusatzelement dient, empfängt der Funktions Indikator <xref:System.Windows.UIElement.Drop> Eingabe <xref:System.Windows.UIElement.MouseMove>Ereignisse (z. b. oder), die für das zugrunde liegende verzierte Element bestimmt sein können.  Ein Adorner kann bestimmte Eingabeereignisse überwachen und diese durch erneutes Auslösen des Ereignisses an das zugrunde liegende verzierte Element weiterleiten.  
  
 Um Pass-Through-Treffer Tests von Elementen unter einem Adorner zu aktivieren, legen Sie <xref:System.Windows.UIElement.IsHitTestVisible%2A> die Eigenschaft Treffer Test für den Adorner auf **false** fest.  Weitere Informationen zu Treffertests finden Sie unter  
  
 [Treffertests in der visuellen Ebene](../graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
<a name="adorn_single_element"></a>   
## <a name="adorning-a-single-uielement"></a>Verzieren eines einzelnen UIElement-Elements  
 Führen Sie die folgenden Schritte aus, um <xref:System.Windows.UIElement>einen Funktions Indikator an einen bestimmten zu binden:  
  
1. Ruft die statische- <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> Methode auf, <xref:System.Windows.Documents.AdornerLayer> um ein- <xref:System.Windows.UIElement> Objekt zu erhalten, das zu schmücken ist. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>durchläuft die visuelle Struktur, beginnend beim angegebenen <xref:System.Windows.UIElement>und gibt die erste gefundene Adornerebene zurück. (Falls keine Adorner-Ebenen gefunden werden, gibt die Methode NULL zurück.)  
  
2. Ruft die <xref:System.Windows.Documents.AdornerLayer.Add%2A> -Methode auf, um den Funktions Indikator an <xref:System.Windows.UIElement>das Ziel zu binden.  
  
 Im folgenden Beispiel wird ein SimpleCircleAdorner (siehe oben) an ein <xref:System.Windows.Controls.TextBox> benanntes *MyTextBox*-Element gebunden.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
> Das Binden von Adornern an andere Elemente mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird derzeit nicht unterstützt.  
  
<a name="adorn_children_panel"></a>   
## <a name="adorning-the-children-of-a-panel"></a>Verzieren der untergeordneten Elemente eines Panels  
 Führen Sie die folgenden Schritte aus <xref:System.Windows.Controls.Panel>, um einen Funktions Indikator an die untergeordneten Elemente eines zu binden:  
  
1. Ruft die `static` - <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> Methode auf, um eine Adornerebene für das Element zu finden, dessen untergeordnete Elemente geschmückt werden sollen.  
  
2. Listet die untergeordneten Elemente des übergeordneten Elements auf und ruft <xref:System.Windows.Documents.AdornerLayer.Add%2A> die-Methode auf, um einen Funktions Indikator an jedes untergeordnete Element zu binden.  
  
 Im folgenden Beispiel wird ein SimpleCircleAdorner (siehe oben) an die untergeordneten Elemente <xref:System.Windows.Controls.StackPanel> eines namens *myStackPanel*gebunden.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.AdornerHitTestResult>
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [Übersicht über Zeichnungsobjekte](../graphics-multimedia/drawing-objects-overview.md)
- [Themen zu Vorgehensweisen](adorners-how-to-topics.md)
