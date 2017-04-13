---
title: "Gewusst wie: Festlegen einer Eigenschaft nach einer Storyboard-Animation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Animation, Ändern der Eigenschaftswerte nach"
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Festlegen einer Eigenschaft nach einer Storyboard-Animation
In einigen Fällen kann es so aussehen, als ob Sie den Wert einer Eigenschaft nicht ändern können, nachdem sie animiert wurde.  
  
## Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.Animation.Storyboard> verwendet, um die Farbe für <xref:System.Windows.Media.SolidColorBrush> zu animieren.  Das Storyboard wird ausgelöst, wenn auf die Schaltfläche geklickt wird.  Das <xref:System.Windows.Media.Animation.Timeline.Completed>\-Ereignis wird so behandelt, dass das Programm benachrichtigt wird, wenn der <xref:System.Windows.Media.Animation.ColorAnimation>\-Vorgang abgeschlossen ist.  
  
 [!code-xml[timingbehaviors_snip#GraphicsMMButton1Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## Beispiel  
 Nachdem der <xref:System.Windows.Media.Animation.ColorAnimation>\-Vorgang abgeschlossen wurde, versucht das Programm, die Farbe des Pinsels in Blau zu ändern.  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 Es erscheint, als ob der vorherige Code keine Auswirkung hat: Der Pinsel bleibt gelb, also auf dem Wert, der von <xref:System.Windows.Media.Animation.ColorAnimation> als Animation des Pinsels angegeben wurde.  Tatsächlich wird jedoch der zugrunde liegende Eigenschaftswert \(der Basiswert\) in Blau geändert.  Der aktive bzw. der aktuelle Wert bleibt jedoch der Wert für Gelb, weil <xref:System.Windows.Media.Animation.ColorAnimation> den Basiswert noch überschreibt.  Wenn Sie möchten, dass der Basiswert wieder zum aktiven Wert wird, müssen Sie es rückgängig machen, dass die sich die Animation auf die Eigenschaft auswirkt.  Es gibt drei Möglichkeiten, dies bei Storyboard\-Animationen zu erreichen:  
  
-   Legen Sie die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>\-Eigenschaft der Animation auf den Wert <xref:System.Windows.Media.Animation.FillBehavior> fest.  
  
-   Entfernen Sie das gesamte Storyboard.  
  
-   Entfernen Sie die Animation aus der jeweiligen Eigenschaft.  
  
## Festlegen der FillBehavior\-Eigenschaft der Animation auf "Stop"  
 Indem Sie <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> auf <xref:System.Windows.Media.Animation.FillBehavior> setzen, weisen Sie die Animation an, nicht mehr auf die Zieleigenschaft zu wirken, nachdem das Ende des Aktivitätszeitraums erreicht wurde.  
  
 [!code-xml[timingbehaviors_snip#GraphicsMMButton2Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## Entfernen des gesamten Storyboards  
 Indem Sie einen <xref:System.Windows.Media.Animation.RemoveStoryboard>\-Trigger oder die <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=fullName>\-Methode verwenden, weisen Sie die Storyboard\-Animationen an, nicht mehr auf ihre Zieleigenschaften zu wirken.  Der Unterschied zwischen diesem Ansatz und dem Festlegen der <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>\-Eigenschaft besteht darin, dass Sie das Storyboard jederzeit entfernen können, während sich die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>\-Eigenschaft nur auswirkt, nachdem die Animation das Ende ihres Aktivitätszeitraums erreicht hat.  
  
 [!code-xml[timingbehaviors_snip#GraphicsMMButton3Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## Entfernen einer Animation aus einer einzelnen Eigenschaft  
 Ein anderes Verfahren zum Beenden der Auswirkung einer Animation auf eine Eigenschaft ist die Verwendung der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29>\-Methode des Objekts, das animiert wird.  Geben Sie die animierte Eigenschaft als ersten Parameter und `null` als zweiten Parameter an.  
  
 [!code-xml[timingbehaviors_snip#GraphicsMMButton4Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 Dieses Verfahren funktioniert auch für Animationen ohne Storyboard.  
  
## Siehe auch  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>   
 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=fullName>   
 <xref:System.Windows.Media.Animation.RemoveStoryboard>   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)