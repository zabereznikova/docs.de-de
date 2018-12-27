---
title: 'Vorgehensweise: Animieren der Durchlässigkeit eines Elements oder eines Pinsels'
ms.date: 03/30/2017
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
ms.openlocfilehash: 659b051fe63c113bf1a4488b1fab12bbee75b1e3
ms.sourcegitcommit: 882a2f56bf6afdcb40d468e4ae9371296822b68c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2018
ms.locfileid: "53451247"
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a>Vorgehensweise: Animieren der Durchlässigkeit eines Elements oder eines Pinsels
Um ein FrameworkElement ein-und auszublenden, animieren Sie dessen <xref:System.Windows.UIElement.Opacity%2A> -Eigenschaft, oder Sie können Animieren der <xref:System.Windows.Media.Brush.Opacity%2A> Eigenschaft der <xref:System.Windows.Media.Brush> (oder Pinsel) verwendet, um es zu zeichnen. Animieren der Durchlässigkeit des Elements können sie und ihren untergeordneten Elementen ein-und ausgeblendet, aber den Pinsel ab, die zum Zeichnen des Elements animieren, können Sie zum welcher Bereich des Elements wird ausgeblendet. Sie können z. B. die Deckkraft eines Pinsels, der zum Zeichnen des Hintergrunds einer Schaltfläche verwendete animieren. Dadurch würde der Hintergrund der Schaltfläche auf der Ansicht, bleiben dessen Text vollständig deckend ein-und ausgeblendet.  
  
> [!NOTE]
>  Animieren der <xref:System.Windows.Media.Brush.Opacity%2A> von einer <xref:System.Windows.Media.Brush> bietet Leistungsvorteile gegenüber Animieren der <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft eines Elements.  
  
 Im folgenden Beispiel werden zwei Schaltflächen animiert, damit sie ein-und auszublenden. Die Durchlässigkeit des ersten <xref:System.Windows.Controls.Button> aus animiert `1.0` zu `0.0` über eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von fünf Sekunden. Die zweite Schaltfläche ist auch animiert, aber die Durchlässigkeit des Pinsels geändert, die zum Zeichnen verwendete seine <xref:System.Windows.Controls.Control.Background%2A> wird anstelle der Durchlässigkeit der gesamten Schaltfläche animiert. Wenn das Beispiel ausgeführt wird, dass die erste Schaltfläche ein-und, vollständig ein, und zwar nur der Hintergrund der zweiten Schaltfläche ein-und ausgeblendet wird. Text und Rahmen bleibt vollständig deckend ist.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 In diesem Beispiel wurde Code ausgelassen. Das vollständige Beispiel zeigt außerdem das Animieren der Durchlässigkeit einer <xref:System.Windows.Media.Color> innerhalb einer <xref:System.Windows.Media.LinearGradientBrush>.  Das vollständige Beispiel finden Sie unter den [animieren die Durchlässigkeit eines Elements Beispiels](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/OpacityAnimation).
