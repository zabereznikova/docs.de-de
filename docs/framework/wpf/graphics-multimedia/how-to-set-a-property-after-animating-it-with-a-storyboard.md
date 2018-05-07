---
title: 'Gewusst wie: Festlegen einer Eigenschaft nach einer Storyboard-Animation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
ms.openlocfilehash: b8e9c08075b13f8d6f701d5ac6ae4f8ea8949184
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a>Gewusst wie: Festlegen einer Eigenschaft nach einer Storyboard-Animation
In einigen Fällen könnte es scheinen, dass Sie den Wert einer Eigenschaft ändern können, nachdem sie animiert wurde.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel ein <xref:System.Windows.Media.Animation.Storyboard> wird verwendet, um die Farbe des Animieren einer <xref:System.Windows.Media.SolidColorBrush>. Das Storyboard wird ausgelöst, wenn die Schaltfläche geklickt wird. Die <xref:System.Windows.Media.Animation.Timeline.Completed> -Ereignis behandelt wird, damit das Programm benachrichtigt wird, wenn die <xref:System.Windows.Media.Animation.ColorAnimation> abgeschlossen ist.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a>Beispiel  
 Nach der <xref:System.Windows.Media.Animation.ColorAnimation> abgeschlossen ist, versucht das Programm, das die Farbe des Pinsels in Blau zu ändern.  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 Der vorherige Code ist scheinbar nicht nichts zu tun: die Pinsel bleibt gelb, das den Wert von bereitgestellten der <xref:System.Windows.Media.Animation.ColorAnimation> , der den Pinsel animiert. Die zugrunde liegende Eigenschaftswert (Preis) ist tatsächlich Blau geändert. Der effektive bzw. der aktuelle Wert bleibt jedoch Gelb da die <xref:System.Windows.Media.Animation.ColorAnimation> ist den Basiswert noch überschreiben. Gegebenenfalls den Basiswert der effektive Wert erneut zu, müssen Sie die Animation aus Schätzung vor bzw. beeinflusst die Eigenschaft beenden. Es gibt drei Möglichkeiten, dies mit Storyboard-Animationen umzusetzen:  
  
-   Legen Sie der Animation <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft <xref:System.Windows.Media.Animation.FillBehavior.Stop>  
  
-   Entfernen Sie das gesamte Storyboard.  
  
-   Entfernen Sie die Animation aus der jeweiligen Eigenschaft ab.  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a>Legen Sie die Animation FillBehavior-Eigenschaft auf Beenden  
 Durch Festlegen von <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> zu <xref:System.Windows.Media.Animation.FillBehavior.Stop>, teilen Sie die Animation zum Beenden von ihrer Zieleigenschaft beeinflussen, nachdem das Ende des aktiven Zeitraums erreicht.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a>Entfernen Sie das gesamte storyboard  
 Mithilfe einer <xref:System.Windows.Media.Animation.RemoveStoryboard> Trigger oder die <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> -Methode, teilen Sie die Storyboard-Animationen, beenden Sie die Auswirkungen auf die Zieleigenschaften. Der Unterschied zwischen diesem Ansatz und dem Festlegen der <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft ist, Sie das Storyboard entfernen while-jederzeit und auf die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft ist nur wirksam, wenn die Animation das Ende ihres aktiven Zeitraums erreicht.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a>Entfernen einer Animation aus einer einzelnen Eigenschaft  
 Ein anderes Verfahren zum Beenden einer Animation Auswirkungen auf eine Eigenschaft ist die Verwendung der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> -Methode des zu animierenden Objekts. Geben Sie die Eigenschaft als erster Parameter animierten und `null` als das zweite.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 Dieses Verfahren kann auch für nicht-Storyboard-Animationen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Media.Animation.RemoveStoryboard>  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
