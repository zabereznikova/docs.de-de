---
title: 'Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- non-Storyboard animation
- local animation [WPF]
- animation [WPF], non-Storyboard (local)
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
ms.openlocfilehash: 71711c0392576930e97986078ec5926ff6ca9813
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963009"
---
# <a name="how-to-animate-a-property-without-using-a-storyboard"></a>Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard
Dieses Beispiel zeigt eine Möglichkeit, eine Animation auf eine Eigenschaft anzuwenden, ohne zu <xref:System.Windows.Media.Animation.Storyboard>verwenden.  
  
> [!NOTE]
> Diese Funktionalität ist in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] nicht verfügbar. Informationen über das Animieren einer Eigenschaft in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft unter Verwendung eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md).  
  
 Verwenden Sie die <xref:System.Windows.UIElement.BeginAnimation%2A> -Methode, um eine lokale Animation auf eine Eigenschaft anzuwenden. Diese Methode nimmt zwei Parameter an: <xref:System.Windows.DependencyProperty> einen-Wert, der die zu animierende Eigenschaft angibt, und die Animation, die auf diese Eigenschaft angewendet werden soll.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die Breite und die Hintergrundfarbe <xref:System.Windows.Controls.Button>eines animiert werden.  
  
 [!code-cpp[animateproperty#11](~/samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](~/samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 Eine Reihe von Animations Klassen im <xref:System.Windows.Media.Animation> -Namespace sind zum Animieren verschiedener Typen von Eigenschaften vorhanden. Weitere Informationen über das Animieren von Eigenschaften finden Sie unter [Übersicht über Animationen](animation-overview.md). Weitere Informationen über Abhängigkeitseigenschaften (der Eigenschaftentyp, der in diesen Beispielen verwendet wird) und ihre Funktionen finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../advanced/dependency-properties-overview.md).  
  
 Es gibt weitere Möglichkeiten, ohne <xref:System.Windows.Media.Animation.Storyboard> Objekte zu animieren. Weitere Informationen finden Sie unter [Übersicht über die Eigenschaften Animationstechniken](property-animation-techniques-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.AnimationTimeline>
- <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Übersicht über die Verfahren zur Animation von Eigenschaften](property-animation-techniques-overview.md)
- [Übersicht über Animationen](animation-overview.md)
