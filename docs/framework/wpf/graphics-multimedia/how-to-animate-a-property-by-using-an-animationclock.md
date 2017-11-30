---
title: 'Gewusst wie: Animieren einer Eigenschaft mit AnimationClock'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 47df7aaad45000bc8c761a9bb9022d37e0f0828c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a>Gewusst wie: Animieren einer Eigenschaft mit AnimationClock
Dieses Beispiel zeigt, wie <xref:System.Windows.Media.Animation.Clock> -Objekten, die eine Eigenschaft animiert werden soll.  
  
 Es gibt drei Möglichkeiten, eine Abhängigkeitseigenschaft zu animieren:  
  
-   Erstellen einer <xref:System.Windows.Media.Animation.AnimationTimeline> und ordnen sie dieser Eigenschaft mit einem <xref:System.Windows.Media.Animation.Storyboard>.  
  
-   Verwenden Sie das Objekt <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode, um ein einzelnes anzuwenden <xref:System.Windows.Media.Animation.AnimationTimeline> auf eine Zieleigenschaft.  
  
-   Erstellen einer <xref:System.Windows.Media.Animation.AnimationClock> aus einem <xref:System.Windows.Media.Animation.AnimationTimeline> und auf eine Eigenschaft angewendet.  
  
 <xref:System.Windows.Media.Animation.Storyboard>Objekte und die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode ermöglichen es Ihnen, Eigenschaften animieren, ohne direkt zu erstellen und Verteilen von Uhren (Beispiele finden Sie unter [Animieren einer Eigenschaft eines Drehbuchs mit](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) und [Animieren einer Eigenschaft ohne Ein Storyboard mit](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)); Uhren erstellt und verteilt werden automatisch für Sie.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Media.Animation.AnimationClock> und auf zwei ähnliche Eigenschaften angewendet.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Ein Beispiel, das zeigt, wie Sie interaktiv steuern eine <xref:System.Windows.Media.Animation.Clock> nach dem Start, finden Sie unter [interaktiv steuern eine Uhr](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [Animieren einer Eigenschaft ohne Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)  
 [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
