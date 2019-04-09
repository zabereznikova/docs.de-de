---
title: 'Vorgehensweise: Festlegen einer Eigenschaft nach einer Storyboard-Animation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
ms.openlocfilehash: 2e1389392c6465ed56b2c71e53b2e3c1947acbe2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188310"
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a>Vorgehensweise: Festlegen einer Eigenschaft nach einer Storyboard-Animation
In einigen Fällen kann es so aussehen, dass Sie den Wert einer Eigenschaft ändern können, nachdem sie animiert wurde.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel eine <xref:System.Windows.Media.Animation.Storyboard> wird verwendet, um die Farbe des Animieren einer <xref:System.Windows.Media.SolidColorBrush>. Das Storyboard wird ausgelöst, wenn die Schaltfläche geklickt wird. Die <xref:System.Windows.Media.Animation.Timeline.Completed> -Ereignis behandelt, damit die Anwendung benachrichtigt wird, wenn die <xref:System.Windows.Media.Animation.ColorAnimation> abgeschlossen ist.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a>Beispiel  
 Nach der <xref:System.Windows.Media.Animation.ColorAnimation> abgeschlossen ist, versucht das Programm, das die Farbe des Pinsels in Blau zu ändern.  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 Der vorherige Code nicht angezeigt werden, nichts weiter tun: Pinsel bleibt die Gelb, das den Wert angegeben wird, indem die <xref:System.Windows.Media.Animation.ColorAnimation> , die den Pinsel animiert. Der zugrunde liegende Eigenschaftswert (der Basiswert) ist tatsächlich Blau geändert. Der effektive bzw. der aktuelle Wert bleibt jedoch gelben da die <xref:System.Windows.Media.Animation.ColorAnimation> noch den Basiswert überschreibt. Wenn Sie den Basiswert der effektive Wert erneut werden möchten, müssen Sie die Animation einen Einfluss auf die Eigenschaft beenden. Es gibt drei Möglichkeiten, dies mit der Storyboard-Animationen umzusetzen:  
  
-   Festlegen der Animation <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft <xref:System.Windows.Media.Animation.FillBehavior.Stop>  
  
-   Entfernen Sie das gesamte Storyboard an.  
  
-   Entfernen Sie die Animation, aus der jeweiligen Eigenschaft.  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a>Festlegen von FillBehavior-Eigenschaft der Animation beendet  
 Durch Festlegen von <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> zu <xref:System.Windows.Media.Animation.FillBehavior.Stop>, Sie erkennen, dass die Animation beendet wird, auf die Zieleigenschaft, nachdem das Ende des aktiven Zeitraums erreicht.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a>Entfernen Sie das gesamte storyboard  
 Mithilfe einer <xref:System.Windows.Media.Animation.RemoveStoryboard> Trigger oder die <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> -Methode, teilen Sie die Storyboard-Animationen, um Auswirkungen auf deren Zieleigenschaften zu beenden. Der Unterschied zwischen diesem Ansatz und die Einstellung der <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft ist, dass Sie das Storyboard entfernen können jederzeit und an zwar die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft hat nur Auswirkungen, wenn die Animation das Ende des aktiven Zeitraums erreicht hat.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a>Entfernen einer Animation aus einer einzelnen Eigenschaft  
 Ein anderes Verfahren zum Beenden einer Animation Auswirkungen auf eine Eigenschaft ist die Verwendung der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> -Methode des animierten Objekts. Geben Sie die zu animierende Eigenschaft als ersten Parameter und `null` als das zweite.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 Dieses Verfahren funktioniert auch für nicht-Storyboard-Animationen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.Animation.RemoveStoryboard>
- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über die Verfahren zur Animation von Eigenschaften](property-animation-techniques-overview.md)
