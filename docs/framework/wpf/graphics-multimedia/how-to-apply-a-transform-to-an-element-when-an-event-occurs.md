---
title: 'Gewusst wie: Anwenden einer Transformation auf ein Element beim Auftreten eines Ereignisses'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
ms.openlocfilehash: bd50b369666a1b65226b2b7eb6f3d866ec670bde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a>Gewusst wie: Anwenden einer Transformation auf ein Element beim Auftreten eines Ereignisses
In diesem Beispiel wird gezeigt, wie zum Anwenden einer <xref:System.Windows.Media.ScaleTransform> bei Auftreten eines Ereignisses. Mithilfe des hier dargestellten Konzepts können Sie auch andere Transformationstypen anwenden. Weitere Informationen zu den verfügbaren Typen von Transformationen finden Sie unter der <xref:System.Windows.Media.Transform> Klasse oder [Transforms Overview](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
 Sie können mit einem der folgenden beiden Verfahren eine Transformation auf ein Element anwenden:  
  
-   Wenn Sie dies tun *nicht* möchten Sie die Transformation auf das Layout auswirken, verwenden Sie die <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft des Elements.  
  
-   Wenn Sie die Transformation auf das Layout auswirken soll, verwenden Sie die <xref:System.Windows.FrameworkElement.LayoutTransform%2A> -Eigenschaft des Elements.  
  
 Das folgende Beispiel wendet eine <xref:System.Windows.Media.ScaleTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft einer Schaltfläche. Beim Bewegen der Maus auf die Schaltfläche der <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> Eigenschaften der <xref:System.Windows.Media.ScaleTransform> festgelegt `2`, dies bedeutet, dass die Schaltfläche größer wird. Wenn die Maus bewegt wird, deaktiviert die Schaltfläche <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> festgelegt `1`, dies bedeutet, dass die Schaltfläche, um die ursprüngliche Größe zurück.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[ButtonTransform#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)  
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
