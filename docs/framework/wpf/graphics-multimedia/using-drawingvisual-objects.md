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
ms.openlocfilehash: 9d67fbc0d9716c9df3935232c6c7e579b50d55bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148321"
---
# <a name="using-drawingvisual-objects"></a>Verwenden von DrawingVisual-Objekten
Dieses Thema bietet einen Überblick <xref:System.Windows.Media.DrawingVisual> über [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Verwendung von Objekten in der visuellen Ebene.  
  
<a name="drawingvisual_object"></a>
## <a name="drawingvisual-object"></a>DrawingVisual-Objekt  
 Die <xref:System.Windows.Media.DrawingVisual> ist eine einfache Zeichnungsklasse, die zum Rendern von Formen, Bildern oder Text verwendet wird. Diese Klasse wird als einfach angesehen, weil sie weder Layout noch Ereignisbehandlung bereitstellt. Dadurch wird die Leistung gesteigert. Aus diesem Grund eignen sich Zeichnungen für Hintergründe und ClipArt.  
  
<a name="drawingvisual_host_container"></a>
## <a name="drawingvisual-host-container"></a>DrawingVisual-Hostcontainer  
 Um Objekte <xref:System.Windows.Media.DrawingVisual> verwenden zu können, müssen Sie einen Hostcontainer für die Objekte erstellen. Das Hostcontainerobjekt muss von <xref:System.Windows.FrameworkElement> der Klasse abstammen, die das <xref:System.Windows.Media.DrawingVisual> Layout und die Ereignisbehandlung unterstützt, die der Klasse fehlen. Das Hostcontainerobjekt zeigt keine sichtbaren Eigenschaften, da seine Hauptfunktion die Aufnahme untergeordneter Objekte ist. Die <xref:System.Windows.UIElement.Visibility%2A> Eigenschaft des Hostcontainers muss jedoch <xref:System.Windows.Visibility.Visible>auf festgelegt werden. Andernfalls ist keines der untergeordneten Elemente sichtbar.  
  
 Wenn Sie ein Hostcontainerobjekt für visuelle Objekte erstellen, müssen <xref:System.Windows.Media.VisualCollection>Sie die visuellen Objektverweise in einem speichern. Verwenden <xref:System.Windows.Media.VisualCollection.Add%2A> Sie die Methode, um dem Hostcontainer ein visuelles Objekt hinzuzufügen. Im folgenden Beispiel wird ein Hostcontainerobjekt erstellt, und drei <xref:System.Windows.Media.VisualCollection>visuelle Objekte werden seiner hinzugefügt.  
  
 [!code-csharp[DrawingVisualSample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
> Informationen über das vollständige Codebeispiel, aus dem das vorherige Codebeispiel extrahiert wurde, finden Sie unter [Beispiel für Treffertests mit DrawingVisuals](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).  
  
<a name="creating_drawingvisual_objects"></a>
## <a name="creating-drawingvisual-objects"></a>Erstellen von DrawingVisual-Objekten  
 Wenn Sie <xref:System.Windows.Media.DrawingVisual> ein Objekt erstellen, hat es keinen Zeichnungsinhalt. Sie können Text, Grafiken oder Bildinhalte hinzufügen, <xref:System.Windows.Media.DrawingContext> indem Sie die Objekte abrufen und in das Objekt zeichnen. A <xref:System.Windows.Media.DrawingContext> wird zurückgegeben, <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> indem <xref:System.Windows.Media.DrawingVisual> die Methode eines Objekts aufgerufen wird.  
  
 Um ein Rechteck <xref:System.Windows.Media.DrawingContext>in die <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> zu <xref:System.Windows.Media.DrawingContext> zeichnen, verwenden Sie die Methode des Objekts. Ähnliche Methoden sind für andere Arten von Inhalten verfügbar. Wenn Sie mit dem <xref:System.Windows.Media.DrawingContext>Zeichnen von <xref:System.Windows.Media.DrawingContext.Close%2A> Inhalten in <xref:System.Windows.Media.DrawingContext> die fertig sind, rufen Sie die Methode auf, um den Inhalt zu schließen und beizubehalten.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.DrawingVisual> wird ein Objekt erstellt, und <xref:System.Windows.Media.DrawingContext>ein Rechteck wird in seine gezeichnet.  
  
 [!code-csharp[DrawingVisualSample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>
## <a name="creating-overrides-for-frameworkelement-members"></a>Erstellen von Überschreibungen für Elemente von FrameworkElement  
 Der Hostcontainerobjekt ist für die Verwaltung seiner Auflistung von visuellen Objekten zuständig. Dies erfordert, dass der Hostcontainer-Implement-Member für die abgeleitete <xref:System.Windows.FrameworkElement> Klasse überschreibt.  
  
 Die folgende Liste beschreibt die zwei Elemente, die Sie überschreiben müssen:  
  
- <xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Gibt ein untergeordnetes Element am angegebenen Index aus der Auflistung untergeordneter Elemente zurück.  
  
- <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Ruft die Anzahl der visuellen untergeordneten Elemente in diesem Element ab.  
  
 Im folgenden Beispiel werden Überschreibungen für die beiden <xref:System.Windows.FrameworkElement> Member implementiert.  
  
 [!code-csharp[DrawingVisualSample#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>
## <a name="providing-hit-testing-support"></a>Bereitstellen von Unterstützung für den Treffertest  
 Das Hostcontainerobjekt kann die Ereignisbehandlung auch dann bereitstellen, wenn <xref:System.Windows.UIElement.Visibility%2A> keine sichtbaren <xref:System.Windows.Visibility.Visible>Eigenschaften angezeigt werden. Dadurch können Sie eine Ereignisbehandlungsroutine für den Hostcontainer erstellen, die Mausereignisse, z.B. das Loslassen der linken Maustaste, auffangen kann. Die Ereignisbehandlungsroutine kann dann Treffertests implementieren, indem sie die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methode aufruft. Der <xref:System.Windows.Media.HitTestResultCallback> Parameter der Methode bezieht sich auf eine benutzerdefinierte Prozedur, mit der Sie die resultierende Aktion eines Treffertests bestimmen können.  
  
 Im folgenden Beispiel wird die Unterstützung für Treffertests für das Hostcontainerobjekt und seine untergeordneten Elemente implementiert.  
  
 [!code-csharp[DrawingVisualSample#103](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.DrawingVisual>
- <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>
- [Übersicht über das WPF-Grafikrendering](wpf-graphics-rendering-overview.md)
- [Treffertests in der visuellen Ebene](hit-testing-in-the-visual-layer.md)
