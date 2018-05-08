---
title: Übersicht über Adorner
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: 6dd38b9e24b42de8945c0e9729f8f30cf901fc3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="adorners-overview"></a>Übersicht über Adorner
Adorner sind eine besondere Art von <xref:System.Windows.FrameworkElement>, wird verwendet, um visuelle Hinweise für einen Benutzer bereitzustellen. Adorner können unter anderem verwendet werden, um Elementen funktionale Ziehpunkte hinzuzufügen oder Zustandsinformationen über Steuerelemente bereitzustellen.  
  
  
  
<a name="about_Adorners"></a>   
## <a name="about-adorners"></a>Informationen über Adorner  
 Ein <xref:System.Windows.Documents.Adorner> ist ein benutzerdefiniertes <xref:System.Windows.FrameworkElement> , gebunden ist, um eine <xref:System.Windows.UIElement>. Funktionsindikatoren werden gerendert, eine <xref:System.Windows.Documents.AdornerLayer>, also in einer Renderingoberfläche, die ständig auf dem erweiterten Element oder eine Auflistung von erweiterten Elementen ist. Die Darstellung von Adorner ist unabhängig von der Darstellung von der <xref:System.Windows.UIElement> , die die Adorner gebunden wird. Ein Adorner wird in der Regel relativ zum Element positioniert, an das er gebunden ist. Dazu wird ein 2D-Standardkoordinatenursprung verwendet, der sich in der oberen linken Ecke des verzierten Elements befindet.  
  
 Adorner finden eine breite Anwendung in folgenden Fällen:  
  
-   Hinzufügen von funktionalen Handles für eine <xref:System.Windows.UIElement> , mit denen einen Benutzer das Element in irgendeiner Form (Ändern der Größe, drehen, neu positionieren, usw.) zu bearbeiten.  
  
-   Bereitstellen von visuellem Feedback, um verschiedene Zustände anzugeben oder auf verschiedene Ereignisse zu reagieren.  
  
-   Überlagern Sie die visual Ergänzungen, die auf eine <xref:System.Windows.UIElement>.  
  
-   Visuell zu maskieren oder außer Kraft setzen oder teilweise eine <xref:System.Windows.UIElement>.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt ein grundlegendes Framework zum Verzieren von visuellen Elementen bereit. In der folgenden Tabelle sind die zum Verzieren von Objekten verwendeten primären Typen samt deren Zweck aufgelistet. Es folgen mehrere Verwendungsbeispiele.  
  
|||  
|-|-|  
|<xref:System.Windows.Documents.Adorner>|Eine abstrakte Basisklasse, von der alle einzelnen Adornerimplementierungen geerbt werden.|  
|<xref:System.Windows.Documents.AdornerLayer>|Eine Klasse, die eine Rendering-Ebene für den (die) Adorner eines oder mehrerer verzierten Elementen darstellt.|  
|<xref:System.Windows.Documents.AdornerDecorator>|Eine Klasse, mit der eine Adorner-Ebene einer Auflistung von Elementen zugeordnet werden kann.|  
  
<a name="implement_custom_Adorner"></a>   
## <a name="implementing-a-custom-adorner"></a>Implementierung eines benutzerdefinierten Adorners  
 Das von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bereitgestellte Adorner-Framework dient in erster Linie der Unterstützung beim Erstellen benutzerdefinierter Adorner. Ein benutzerdefinierter Adorner wird erstellt, durch die Implementierung einer Klasse, die von der abstrakten erbt <xref:System.Windows.Documents.Adorner> Klasse.  
  
> [!NOTE]
>  Das übergeordnete Element des ein <xref:System.Windows.Documents.Adorner> ist die <xref:System.Windows.Documents.AdornerLayer> , rendert die <xref:System.Windows.Documents.Adorner>, nicht das Element, das gestaltet wird.  
  
 Im folgenden Beispiel wird eine Klasse dargestellt, in der ein einfacher Adorner implementiert wird. Beispieladorner werden einfach die Ecken des eine <xref:System.Windows.UIElement> mit Kreisen.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
 Die folgende Abbildung zeigt die SimpleCircleAdorner angewendet, um eine <xref:System.Windows.Controls.TextBox>.  
  
 ![Beispiel für einen Adorner: Eine verzierte TextBox](../../../../docs/framework/wpf/controls/media/adornedtextbox.png "AdornedTextBox")  
  
<a name="rendering_behavior_for_Adorners"></a>   
## <a name="rendering-behavior-for-adorners"></a>Renderingverhalten der Adorner  
 Beachten Sie, dass für Adorner kein Renderingverhalten festgelegt ist. Damit wird sichergestellt, dass für das Rendering die Adorner-Implementierung verantwortlich ist.   Ist eine allgemeine Möglichkeit zum Implementieren von Renderingverhalten überschreiben die <xref:System.Windows.UIElement.OnRender%2A> -Methode, und verwenden Sie eine oder mehrere <xref:System.Windows.Media.DrawingContext> Objekte zum Rendern der Funktionsindikator visuelle Elemente nach Bedarf (wie im obigen Beispiel gezeigt).  
  
> [!NOTE]
>  Sämtliche Elemente auf der Adorner-Ebene werden vor allen anderen Stilen gerendert, die Sie festgelegt haben. Anders gesagt, befinden sich Adorner visuell stets im Vordergrund und können in der Z-Reihenfolge nicht überschrieben werden.  
  
<a name="adorner_events_hittest"></a>   
## <a name="events-and-hit-testing"></a>Ereignisse und Treffertests  
 Adorner empfangen Eingabeereignisse genau wie alle anderen <xref:System.Windows.FrameworkElement>.  Da ein Adorner immer höheren Z-Reihenfolge als das Element es erweitert hat, empfängt der Adorner Eingabeereignisse (z. B. <xref:System.Windows.UIElement.Drop> oder <xref:System.Windows.UIElement.MouseMove>), die möglicherweise für die zugrunde liegende Element dargestellte gedacht sein.  Ein Adorner kann bestimmte Eingabeereignisse überwachen und diese durch erneutes Auslösen des Ereignisses an das zugrunde liegende verzierte Element weiterleiten.  
  
 Legen Sie zum Aktivieren der Pass-Through-Treffertests von Elementen unter einem Adorner Treffertest <xref:System.Windows.UIElement.IsHitTestVisible%2A> Eigenschaft **"false"** für den Adorner.  Weitere Informationen zu Treffertests finden Sie unter  
  
 [Treffertests in der visuellen Ebene](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
<a name="adorn_single_element"></a>   
## <a name="adorning-a-single-uielement"></a>Verzieren eines einzelnen UIElement-Elements  
 So binden einen Adorner zu einem bestimmten <xref:System.Windows.UIElement>, gehen Sie folgendermaßen vor:  
  
1.  Rufen Sie die statische Methode <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> zum Abrufen einer <xref:System.Windows.Documents.AdornerLayer> -Objekt für die <xref:System.Windows.UIElement> zu gestaltet werden. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> durchläuft die visuelle Struktur, beginnend am angegebenen <xref:System.Windows.UIElement>, und gibt die erste Adornerebene gefunden. (Falls keine Adorner-Ebenen gefunden werden, gibt die Methode NULL zurück.)  
  
2.  Rufen Sie die <xref:System.Windows.Documents.AdornerLayer.Add%2A> Methode, um den Adorner an das Ziel binden <xref:System.Windows.UIElement>.  
  
 Im folgende Beispiel wird ein SimpleCircleAdorner, die (siehe oben), um eine <xref:System.Windows.Controls.TextBox> mit dem Namen *MyTextBox*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  Das Binden von Adornern an andere Elemente mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird derzeit nicht unterstützt.  
  
<a name="adorn_children_panel"></a>   
## <a name="adorning-the-children-of-a-panel"></a>Verzieren der untergeordneten Elemente eines Panels  
 So binden Sie einen Adorner an die untergeordneten Elemente einer <xref:System.Windows.Controls.Panel>, gehen Sie folgendermaßen vor:  
  
1.  Rufen Sie die `static` Methode <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> eine Adornerebene für das Element gefunden, deren untergeordnete Elemente sind, gestaltet werden.  
  
2.  Durchlaufen der untergeordneten Elemente des übergeordneten Elements, und rufen die <xref:System.Windows.Documents.AdornerLayer.Add%2A> Methode, um einen Adorner an jedes untergeordnete Element binden.  
  
 Im folgenden Beispiel bindet ein SimpleCircleAdorner (siehe oben) auf die untergeordneten eine <xref:System.Windows.Controls.StackPanel> mit dem Namen *MyStackPanel*.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.AdornerHitTestResult>  
 [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/adorners-how-to-topics.md)
