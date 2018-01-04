---
title: 'Gewusst wie: Angeben des Ursprungs einer Transformation mithilfe von relativen Werten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d29a572e2989ffb800434fdaab9756cb651c0816
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a>Gewusst wie: Angeben des Ursprungs einer Transformation mithilfe von relativen Werten
Dieses Beispiel veranschaulicht die relativen Werte verwenden, um den Ursprung der angeben einer <xref:System.Windows.UIElement.RenderTransform%2A> angewendeten eine <xref:System.Windows.FrameworkElement>.  
  
 Wenn Sie drehen, skalieren oder verzerren ein <xref:System.Windows.FrameworkElement> mithilfe der <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft, die Standardeinstellung wendet die Transformation auf der linken oberen Ecke des Elements. Wenn Sie von der Mitte des Elements aus drehen, skalieren oder neigen möchten, können Sie dies ändern, indem Sie für den Mittelpunkt der Transformation den Mittelpunkt des Elements festlegen. Für diese Lösung müssen Sie jedoch die Größe des Elements kennen. Eine einfachere Möglichkeit, eine Transformation anwenden, in der Mitte eines Elements festgelegt wird seine <xref:System.Windows.UIElement.RenderTransformOrigin%2A> Eigenschaft (0,5, 0,5), anstatt eine Center-Einstellung auf die Transformation selbst.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.RotateTransform> Rotieren einer <xref:System.Windows.Controls.Button> 45 Grad im Uhrzeigersinn. Da in dem Beispiel kein Mittelpunkt angegeben ist, dreht sich die Schaltfläche um den Punkt (0, 0), die obere linke Ecke. Die <xref:System.Windows.Media.RotateTransform> wird angewendet, um die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft.  
  
 In der folgenden Abbildung wird das Transformationsergebnis für das folgende Beispiel angezeigt.  
  
 ![Eine mit RenderTransform transformierte Schaltfläche](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "Graphicsmm_RenderTransformWithDefaultCenter")  
Eine Drehung um 45 Grad im Uhrzeigersinn unter Verwendung der RenderTransform-Eigenschaft  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 Auch im folgenden Beispiel wird eine <xref:System.Windows.Media.RotateTransform> drehen eine <xref:System.Windows.Controls.Button> um 45 Grad im Uhrzeigersinn gedreht; allerdings in diesem Beispiel wird die <xref:System.Windows.UIElement.RenderTransformOrigin%2A> der Schaltfläche auf (0,5, 0,5). Dadurch erfolgt die Drehung um den Mittelpunkt der Schaltfläche, nicht um die obere linke Ecke.  
  
 In der folgenden Abbildung wird das Transformationsergebnis für das folgende Beispiel angezeigt.  
  
 ![Eine um ihren Mittelpunkt transformierte Schaltfläche](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "Graphicsmm_RenderTransformRelativeCenter")  
Eine Drehung um 45 Grad unter Verwendung der RenderTransform-Eigenschaft mit einem RenderTransformOrigin von (0.5, 0.5)  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Weitere Informationen zum Transformieren von <xref:System.Windows.FrameworkElement> anzuzeigen, die [Transforms Overview](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Transform>  
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
