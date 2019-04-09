---
title: 'Vorgehensweise: Anwenden einer Transformation auf ein Element beim Auftreten eines Ereignisses'
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
ms.openlocfilehash: 973b9267eaef5d55176633ee80a1dc7f8b043909
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126437"
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a>Vorgehensweise: Anwenden einer Transformation auf ein Element beim Auftreten eines Ereignisses
Dieses Beispiel veranschaulicht das Anwenden einer <xref:System.Windows.Media.ScaleTransform> bei Auftreten eines Ereignisses. Mithilfe des hier dargestellten Konzepts können Sie auch andere Transformationstypen anwenden. Weitere Informationen zu den verfügbaren Arten von Transformationen, finden Sie unter den <xref:System.Windows.Media.Transform> Klasse oder [Übersicht über Transformationen](transforms-overview.md).  
  
 Sie können mit einem der folgenden beiden Verfahren eine Transformation auf ein Element anwenden:  
  
-   Wenn Sie dies tun *nicht* die Transformation verwenden, um auf das Layout auswirken soll die <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft des Elements.  
  
-   Wenn Sie mit der Transformation auf das Layout auswirken soll, verwenden Sie die <xref:System.Windows.FrameworkElement.LayoutTransform%2A> -Eigenschaft des Elements.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.ScaleTransform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft einer Schaltfläche. Wenn die Maus über die Schaltfläche bewegt die <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> Eigenschaften der <xref:System.Windows.Media.ScaleTransform> festgelegt `2`, die bewirkt, dass die Schaltfläche immer größer werden. Wenn die Maus der Schaltfläche weg bewegt <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> festgelegt `1`, die bewirkt, dass der Schaltfläche, um auf seine ursprüngliche Größe zurückzusetzen.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[ButtonTransform#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [Übersicht über Transformationen](transforms-overview.md)
- [Gewusst wie-Themen](transformations-how-to-topics.md)
- [Übersicht über Routingereignisse](../advanced/routed-events-overview.md)
