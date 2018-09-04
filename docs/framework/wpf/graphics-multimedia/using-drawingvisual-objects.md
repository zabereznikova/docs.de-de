---
title: Verwenden von DrawingVisual-Objekten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual layer [WPF], DrawingVisual objects
- DrawingVisual objects in visual layer [WPF]
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
ms.openlocfilehash: 799892424f92782d71b9a35e76d722d1725815ea
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556099"
---
# <a name="using-drawingvisual-objects"></a>Verwenden von DrawingVisual-Objekten
Dieses Thema enthält eine Übersicht über die Verwendung von <xref:System.Windows.Media.DrawingVisual> Objekte in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] visuellen Ebene.  
  
<a name="drawingvisual_object"></a>   
## <a name="drawingvisual-object"></a>DrawingVisual-Objekt  
 Die <xref:System.Windows.Media.DrawingVisual> ist eine einfache Klasse, die zum Rendern von Formen, Bildern oder Text verwendet wird. Diese Klasse wird als einfach angesehen, weil sie weder Layout noch Ereignisbehandlung bereitstellt. Dadurch wird die Leistung gesteigert. Aus diesem Grund sind Zeichnungen für Hintergründe und ClipArt ideal.  
  
<a name="drawingvisual_host_container"></a>   
## <a name="drawingvisual-host-container"></a>DrawingVisual-Hostcontainer  
 Um verwenden <xref:System.Windows.Media.DrawingVisual> Objekte verwenden, müssen Sie einen Hostcontainer für die Objekte zu erstellen. Das Hostcontainerobjekt muss von abgeleitet werden die <xref:System.Windows.FrameworkElement> -Klasse, die bieten Unterstützung für das Layout und die Behandlung von Ereignissen, die die <xref:System.Windows.Media.DrawingVisual> Klasse fehlt. Das Hostcontainerobjekt zeigt keine sichtbaren Eigenschaften, da seine Hauptfunktion die Aufnahme untergeordneter Objekte ist. Allerdings die <xref:System.Windows.UIElement.Visibility%2A> -Eigenschaft des Hostcontainers muss festgelegt werden, um <xref:System.Windows.Visibility.Visible>ist, andernfalls keine untergeordneten Elemente werden angezeigt.  
  
 Wenn Sie ein Hostcontainerobjekt für visuelle Objekte erstellen, müssen Sie zum Speichern der Verweise von visuellen Objekten in einem <xref:System.Windows.Media.VisualCollection>. Verwenden der <xref:System.Windows.Media.VisualCollection.Add%2A> Methode, um dem Hostcontainer ein visuelles Objekt hinzuzufügen. Im folgenden Beispiel wird ein Hostcontainerobjekt erstellt, und drei visuelle Objekte werden hinzugefügt, um die <xref:System.Windows.Media.VisualCollection>.  
  
 [!code-csharp[DrawingVisualSample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
>  Informationen über das vollständige Codebeispiel, aus dem das vorherige Codebeispiel extrahiert wurde, finden Sie unter [Beispiel für Treffertests mit DrawingVisuals](https://go.microsoft.com/fwlink/?LinkID=159994).  
  
<a name="creating_drawingvisual_objects"></a>   
## <a name="creating-drawingvisual-objects"></a>Erstellen von DrawingVisual-Objekten  
 Bei der Erstellung einer <xref:System.Windows.Media.DrawingVisual> Objekt, er hat keinen Zeichnungsinhalt. Sie können Text, Grafiken oder Bildinhalt hinzufügen, durch Abrufen des Objekts <xref:System.Windows.Media.DrawingContext> und die Zeichnung. Ein <xref:System.Windows.Media.DrawingContext> wird zurückgegeben, indem die <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> Methode eine <xref:System.Windows.Media.DrawingVisual> Objekt.  
  
 Zum Zeichnen eines Rechtecks in die <xref:System.Windows.Media.DrawingContext>, verwenden Sie die <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> Methode der <xref:System.Windows.Media.DrawingContext> Objekt. Ähnliche Methoden sind für andere Arten von Inhalten verfügbar. Sie danach Zeichnungsinhalt in die <xref:System.Windows.Media.DrawingContext>, rufen Sie die <xref:System.Windows.Media.DrawingContext.Close%2A> Methode zum Schließen der <xref:System.Windows.Media.DrawingContext> und den Inhalt beizubehalten.  
  
 Im folgenden Beispiel eine <xref:System.Windows.Media.DrawingVisual> Objekt wird erstellt und ein Rechteck gezeichnet wird, in dessen <xref:System.Windows.Media.DrawingContext>.  
  
 [!code-csharp[DrawingVisualSample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## <a name="creating-overrides-for-frameworkelement-members"></a>Erstellen von Überschreibungen für Elemente von FrameworkElement  
 Der Hostcontainerobjekt ist für die Verwaltung seiner Auflistung von visuellen Objekten zuständig. Dies erfordert, dass der Hostcontainer elementüberschreibungen für die abgeleitete implementieren <xref:System.Windows.FrameworkElement> Klasse.  
  
 Die folgende Liste beschreibt die zwei Elemente, die Sie überschreiben müssen:  
  
-   <xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Gibt ein untergeordnetes Element am angegebenen Index aus der Auflistung der untergeordneten Elemente.  
  
-   <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Ruft die Anzahl der sichtbaren untergeordneten Elemente innerhalb dieses Elements.  
  
 Im folgenden Beispiel überschreibt, für die beiden <xref:System.Windows.FrameworkElement> Member werden implementiert.  
  
 [!code-csharp[DrawingVisualSample#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## <a name="providing-hit-testing-support"></a>Bereitstellen von Unterstützung für den Treffertest  
 Das Hostcontainerobjekt ermöglicht eine Ereignisbehandlung, auch wenn es keine sichtbaren Eigenschaften nicht angezeigt wird, jedoch die <xref:System.Windows.UIElement.Visibility%2A> Eigenschaft muss festgelegt werden, um <xref:System.Windows.Visibility.Visible>. Dadurch können Sie eine Ereignisbehandlungsroutine für den Hostcontainer erstellen, die Mausereignisse, z.B. das Loslassen der linken Maustaste, auffangen kann. Die Ereignisbehandlungsroutine kann dann Treffertests durch den Aufruf implementieren die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode. Der Methode <xref:System.Windows.Media.HitTestResultCallback> Parameter verweist auf eine benutzerdefinierte Prozedur, die Sie verwenden können, um die resultierende Aktion eines Treffertests bestimmen.  
  
 Im folgenden Beispiel wird die Unterstützung für Treffertests für das Hostcontainerobjekt und seine untergeordneten Elemente implementiert.  
  
 [!code-csharp[DrawingVisualSample#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.DrawingVisual>  
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>  
 [Übersicht über das WPF-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [Treffertests in der visuellen Ebene](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)
