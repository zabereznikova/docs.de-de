---
title: 'Vorgehensweise: Animieren der Durchlässigkeit eines Elements oder eines Pinsels'
ms.date: 03/30/2017
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
ms.openlocfilehash: 2f18861eb18f81b631245d1d933b7acb1b3e0e42
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950514"
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a>Vorgehensweise: Animieren der Durchlässigkeit eines Elements oder eines Pinsels
Um ein FrameworkElement ein-und auszublenden, können Sie seine <xref:System.Windows.UIElement.Opacity%2A> -Eigenschaft animieren, oder Sie können die-Eigenschaft der <xref:System.Windows.Media.Brush> (oder Pinsel) animieren, die <xref:System.Windows.Media.Brush.Opacity%2A> zum Zeichnen verwendet werden. Durch die Animation der Deckkraft des Elements werden diese und ihre untergeordneten Elemente in der Ansicht ausgeblendet, aber die Animation des zum Zeichnen des Elements verwendeten Pinsels ermöglicht es Ihnen, selektiver zu sein, welcher Teil des Elements ausgeblendet wird. Beispielsweise könnten Sie die Deckkraft eines Pinsels animieren, der zum Zeichnen des Hintergrunds einer Schaltfläche verwendet wird. Dies würde dazu führen, dass der Hintergrund der Schaltfläche ein-und ausgeblendet wird, während der Text nicht vollständig deckend ist.  
  
> [!NOTE]
> Die <xref:System.Windows.Media.Brush.Opacity%2A> Animation des einer <xref:System.Windows.Media.Brush> bietet Leistungsvorteile gegenüber der Animation der <xref:System.Windows.UIElement.Opacity%2A> -Eigenschaft eines Elements.  
  
 Im folgenden Beispiel werden zwei Schaltflächen animiert, sodass Sie in der Ansicht ausgeblendet werden. <xref:System.Windows.Controls.Button> Die Deckkraft des ersten wird von `1.0` bis `0.0` über einen <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von fünf Sekunden animiert. Die zweite Schaltfläche wird ebenfalls animiert, aber die Deckkraft des SolidColorBrush, der zum Zeichnen <xref:System.Windows.Controls.Control.Background%2A> der verwendet wird, wird animiert und nicht die Deckkraft der gesamten Schaltfläche. Wenn das Beispiel ausgeführt wird, wird die erste Schaltfläche vollständig ein-und ausgeblendet, während nur der Hintergrund der zweiten Schaltfläche ein-und ausgeblendet wird. Der Text und der Rahmen bleiben vollständig deckend.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[timingbehaviors_snip#10](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 Code wurde in diesem Beispiel ausgelassen. Das vollständige Beispiel zeigt auch, wie Sie die Deckkraft eines <xref:System.Windows.Media.Color> in einem <xref:System.Windows.Media.LinearGradientBrush>animieren.  Das vollständige Beispiel finden Sie im [Beispiel animieren der Durchlässigkeit eines Elements](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/OpacityAnimation).
