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
ms.openlocfilehash: 4e6fc89b64f7b0acc1a0077708d567eb97e2868e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962829"
---
# <a name="using-drawingvisual-objects"></a>Verwenden von DrawingVisual-Objekten
Dieses Thema enthält eine Übersicht über die Verwendung <xref:System.Windows.Media.DrawingVisual> von Objekten in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] visuellen Schicht.  
  
<a name="drawingvisual_object"></a>   
## <a name="drawingvisual-object"></a>DrawingVisual-Objekt  
 <xref:System.Windows.Media.DrawingVisual> Ist eine vereinfachte Zeichnungs Klasse, die zum Rendering von Formen, Bildern oder Text verwendet wird. Diese Klasse wird als einfach angesehen, weil sie weder Layout noch Ereignisbehandlung bereitstellt. Dadurch wird die Leistung gesteigert. Aus diesem Grund sind Zeichnungen für Hintergründe und ClipArt ideal.  
  
<a name="drawingvisual_host_container"></a>   
## <a name="drawingvisual-host-container"></a>DrawingVisual-Hostcontainer  
 Um-Objekte verwenden <xref:System.Windows.Media.DrawingVisual> zu können, müssen Sie einen Host Container für die-Objekte erstellen. Das Host Container Objekt muss von der <xref:System.Windows.FrameworkElement> -Klasse abgeleitet werden, die die Unterstützung für Layout und Ereignis Behandlung bereitstellt, die der <xref:System.Windows.Media.DrawingVisual> -Klasse fehlt. Das Hostcontainerobjekt zeigt keine sichtbaren Eigenschaften, da seine Hauptfunktion die Aufnahme untergeordneter Objekte ist. Allerdings muss <xref:System.Windows.UIElement.Visibility%2A> die-Eigenschaft des Host Containers auf <xref:System.Windows.Visibility.Visible>festgelegt werden. andernfalls ist keines der untergeordneten Elemente sichtbar.  
  
 Wenn Sie ein Host Container Objekt für visuelle Objekte erstellen, müssen Sie die visuellen Objekt Verweise in einer <xref:System.Windows.Media.VisualCollection>speichern. Verwenden Sie <xref:System.Windows.Media.VisualCollection.Add%2A> die-Methode, um dem Host Container ein visuelles Objekt hinzuzufügen. Im folgenden Beispiel wird ein Host Container Objekt erstellt, und es <xref:System.Windows.Media.VisualCollection>werden drei visuelle Objekte zu hinzugefügt.  
  
 [!code-csharp[DrawingVisualSample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
> Informationen über das vollständige Codebeispiel, aus dem das vorherige Codebeispiel extrahiert wurde, finden Sie unter [Beispiel für Treffertests mit DrawingVisuals](https://go.microsoft.com/fwlink/?LinkID=159994).  
  
<a name="creating_drawingvisual_objects"></a>   
## <a name="creating-drawingvisual-objects"></a>Erstellen von DrawingVisual-Objekten  
 Wenn Sie ein <xref:System.Windows.Media.DrawingVisual> -Objekt erstellen, hat es keinen Zeichnungs Inhalt. Sie können Text, Grafiken oder Bildinhalte hinzufügen, indem Sie das Objekt <xref:System.Windows.Media.DrawingContext> abrufen und darin zeichnen. Eine <xref:System.Windows.Media.DrawingContext> wird durch Aufrufen der <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> -Methode eines <xref:System.Windows.Media.DrawingVisual> -Objekts zurückgegeben.  
  
 Um ein Rechteck in die <xref:System.Windows.Media.DrawingContext>zu zeichnen, verwenden Sie die <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> - <xref:System.Windows.Media.DrawingContext> Methode des-Objekts. Ähnliche Methoden sind für andere Arten von Inhalten verfügbar. Wenn Sie mit dem Zeichnen von Inhalt in <xref:System.Windows.Media.DrawingContext>das fertig sind <xref:System.Windows.Media.DrawingContext.Close%2A> , müssen Sie die <xref:System.Windows.Media.DrawingContext> -Methode zum Schließen der und zum Speichern des Inhalts abrufen.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.DrawingVisual> -Objekt erstellt, und ein Rechteck wird in seinen <xref:System.Windows.Media.DrawingContext>gezeichnet.  
  
 [!code-csharp[DrawingVisualSample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## <a name="creating-overrides-for-frameworkelement-members"></a>Erstellen von Überschreibungen für Elemente von FrameworkElement  
 Der Hostcontainerobjekt ist für die Verwaltung seiner Auflistung von visuellen Objekten zuständig. Dies erfordert, dass der Host Container Member-über Schreibungen für die <xref:System.Windows.FrameworkElement> abgeleitete Klasse implementiert.  
  
 Die folgende Liste beschreibt die zwei Elemente, die Sie überschreiben müssen:  
  
- <xref:System.Windows.FrameworkElement.GetVisualChild%2A>: Gibt ein untergeordnetes Element am angegebenen Index aus der Auflistung der untergeordneten Elemente zurück.  
  
- <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: Ruft die Anzahl der sichtbaren untergeordneten Elemente innerhalb dieses Elements ab.  
  
 Im folgenden Beispiel werden außer Kraft setzungen für die beiden <xref:System.Windows.FrameworkElement> Member implementiert.  
  
 [!code-csharp[DrawingVisualSample#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## <a name="providing-hit-testing-support"></a>Bereitstellen von Unterstützung für den Treffertest  
 Das Host Container Objekt kann die Ereignis Behandlung auch dann bereitstellen, wenn es keine sichtbaren Eigenschaften anzeigt – <xref:System.Windows.UIElement.Visibility%2A> seine-Eigenschaft muss jedoch <xref:System.Windows.Visibility.Visible>auf festgelegt werden. Dadurch können Sie eine Ereignisbehandlungsroutine für den Hostcontainer erstellen, die Mausereignisse, z.B. das Loslassen der linken Maustaste, auffangen kann. Die Ereignis Behandlungs Routine kann dann durch Aufrufen der <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> -Methode Treffer Tests implementieren. Der- <xref:System.Windows.Media.HitTestResultCallback> Parameter der Methode verweist auf eine benutzerdefinierte Prozedur, mit der Sie die resultierende Aktion eines Treffer Tests ermitteln können.  
  
 Im folgenden Beispiel wird die Unterstützung für Treffertests für das Hostcontainerobjekt und seine untergeordneten Elemente implementiert.  
  
 [!code-csharp[DrawingVisualSample#103](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.DrawingVisual>
- <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>
- [Übersicht über das WPF-Grafikrendering](wpf-graphics-rendering-overview.md)
- [Treffertests in der visuellen Ebene](hit-testing-in-the-visual-layer.md)
