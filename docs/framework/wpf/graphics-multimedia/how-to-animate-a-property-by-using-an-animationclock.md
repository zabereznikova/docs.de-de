---
title: 'Vorgehensweise: Animieren einer Eigenschaft mit AnimationClock'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
ms.openlocfilehash: d93f1eb352aef4f5e74512a8deeb0ec3fe7943c0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357182"
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a>Vorgehensweise: Animieren einer Eigenschaft mit AnimationClock
Dieses Beispiel zeigt, wie Sie mit <xref:System.Windows.Media.Animation.Clock> -Objekte zum Animieren einer Eigenschaft.  
  
 Es gibt drei Möglichkeiten, eine Abhängigkeitseigenschaft zu animieren:  
  
-   Erstellen einer <xref:System.Windows.Media.Animation.AnimationTimeline> und ordnen sie dieser Eigenschaft mit einem <xref:System.Windows.Media.Animation.Storyboard>.  
  
-   Verwenden des Objekts <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode zum Anwenden einer einzelnes <xref:System.Windows.Media.Animation.AnimationTimeline> auf eine Zieleigenschaft.  
  
-   Erstellen Sie eine <xref:System.Windows.Media.Animation.AnimationClock> aus einer <xref:System.Windows.Media.Animation.AnimationTimeline> und auf eine Eigenschaft anwenden.  
  
 <xref:System.Windows.Media.Animation.Storyboard> Objekte und die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode können Sie Eigenschaften animieren, ohne direkt zu erstellen und Verteilen von Uhren (Beispiele finden Sie in [Animieren einer Eigenschaft unter Verwendung eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md) und [Animieren einer Eigenschaft ohne Mit einem Storyboard](how-to-animate-a-property-without-using-a-storyboard.md)); Uhren werden erstellt und verteilt automatisch für Sie.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Media.Animation.AnimationClock> und auf zwei ähnliche Eigenschaften angewendet.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Ein Beispiel, das zeigt, wie Sie interaktiv steuern eine <xref:System.Windows.Media.Animation.Clock> nachdem es gestartet wurde, finden Sie unter [Interaktives Steuern einer Uhr](how-to-interactively-control-a-clock.md).  
  
## <a name="see-also"></a>Siehe auch
- [Animieren einer Eigenschaft unter Verwendung eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md)
- [Animieren einer Eigenschaft ohne Storyboard](how-to-animate-a-property-without-using-a-storyboard.md)
- [Übersicht über die Verfahren zur Animation von Eigenschaften](property-animation-techniques-overview.md)
