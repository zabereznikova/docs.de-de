---
title: 'Gewusst wie: Animieren der Durchlässigkeit eines Elements oder eines Pinsels'
ms.date: 03/30/2017
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
ms.openlocfilehash: a45bf0344c10e1214aa5218e25e9bd9a87d5ea60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a>Gewusst wie: Animieren der Durchlässigkeit eines Elements oder eines Pinsels
Um ein FrameworkElement ein-und auszublenden, können Sie animieren seine <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft oder Sie können dem animiert werden soll die <xref:System.Windows.Media.Brush.Opacity%2A> Eigenschaft von der <xref:System.Windows.Media.Brush> (oder Pinsel) verwendet, um es zu zeichnen. Animieren das Element Deckkraft vereinfacht und seine untergeordneten Elemente einblenden und ausblenden, aber Animieren des Pinsels, der zum Zeichnen des Elements verwendet wird, können Sie präziser ausgeblendet, welcher Teil des Elements wird. Sie können z. B. die Deckkraft eines Pinsels zum Zeichnen des Hintergrunds einer Schaltfläche verwendet animieren. Dies würde dazu führen, dass der Hintergrund der Schaltfläche zum ein-und Ausblenden der Ansicht, lassen Sie den Text vollständig deckend.  
  
> [!NOTE]
>  Animieren der <xref:System.Windows.Media.Brush.Opacity%2A> von einem <xref:System.Windows.Media.Brush> bietet Leistungsvorteile gegenüber der Animierung der <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft eines Elements.  
  
 Im folgenden Beispiel werden zwei Schaltflächen animiert, damit sie ein-und auszublenden. Die Deckkraft des ersten <xref:System.Windows.Controls.Button> wird von animiert `1.0` auf `0.0` über eine <xref:System.Windows.Media.Animation.Timeline.Duration%2A> von fünf Sekunden. Die zweite Schaltfläche wird ebenfalls animiert, aber die Deckkraft des Pinsels geändert, die zum Zeichnen verwendet seine <xref:System.Windows.Controls.Control.Background%2A> anstatt die Deckkraft der gesamte Schaltfläche animiert wird. Wenn das Beispiel ausgeführt wird, wird die erste Schaltfläche vollständig in und aus der Ansicht ausgeblendet, während nur der Hintergrund der zweiten Schaltfläche ein-und ausgeblendet wird. Text und Rahmen bleiben vollständig deckend ist.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 Code wurde aus diesem Beispiel ausgelassen. Im vollständige Beispiel wird auch gezeigt, wie die Deckkraft des Animieren einer <xref:System.Windows.Media.Color> innerhalb einer <xref:System.Windows.Media.LinearGradientBrush>.  Das vollständige Beispiel finden Sie unter der [animieren die Deckkraft einer Element-Beispiel](http://go.microsoft.com/fwlink/?LinkID=159968).
