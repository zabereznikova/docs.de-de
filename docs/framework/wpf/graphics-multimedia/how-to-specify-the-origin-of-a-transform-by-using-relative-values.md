---
title: 'Vorgehensweise: Angeben des Ursprungs einer Transformation mithilfe von relativen Werten'
ms.date: 03/30/2017
helpviewer_keywords:
- origins of Transforms [WPF]
- Transforms [WPF], origins of
- graphics [WPF], origins of Transforms
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
ms.openlocfilehash: bdcc17e2d9bf68170c10dd8e35670f3e072a527c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352567"
---
# <a name="how-to-specify-the-origin-of-a-transform-by-using-relative-values"></a>Vorgehensweise: Angeben des Ursprungs einer Transformation mithilfe von relativen Werten
Dieses Beispiel zeigt, wie Sie relative Werte verwenden, um den Ursprung der angeben einer <xref:System.Windows.UIElement.RenderTransform%2A> angewendeten eine <xref:System.Windows.FrameworkElement>.  
  
 Wenn Sie drehen, skalieren oder neigen eine <xref:System.Windows.FrameworkElement> mithilfe der <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft, die Standardeinstellung wendet die Transformation auf der linken oberen Ecke des Elements. Wenn Sie von der Mitte des Elements aus drehen, skalieren oder neigen möchten, können Sie dies ändern, indem Sie für den Mittelpunkt der Transformation den Mittelpunkt des Elements festlegen. Für diese Lösung müssen Sie jedoch die Größe des Elements kennen. Eine einfachere Anwendung einer Transformation in der Mitte des Elements festgelegt wird seine <xref:System.Windows.UIElement.RenderTransformOrigin%2A> Eigenschaft auf (0.5, 0.5) Wert für den Mittelpunkt der Transformation selbst festlegen, statt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.RotateTransform> Rotieren einer <xref:System.Windows.Controls.Button> um 45 Grad im Uhrzeigersinn. Da in dem Beispiel kein Mittelpunkt angegeben ist, dreht sich die Schaltfläche um den Punkt (0, 0), die obere linke Ecke. Die <xref:System.Windows.Media.RotateTransform> gilt, an die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft.  
  
 In der folgenden Abbildung wird das Transformationsergebnis für das folgende Beispiel angezeigt.  
  
 ![Eine mit RenderTransform transformierte Schaltfläche](./media/graphicsmm-rendertransformwithdefaultcenter.png "Graphicsmm_RenderTransformWithDefaultCenter")  
Eine Drehung um 45 Grad im Uhrzeigersinn unter Verwendung der RenderTransform-Eigenschaft  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 Das folgende Beispiel verwendet auch eine <xref:System.Windows.Media.RotateTransform> Rotieren einer <xref:System.Windows.Controls.Button> um 45 Grad im Uhrzeigersinn gedreht; allerdings in diesem Beispiel wird der <xref:System.Windows.UIElement.RenderTransformOrigin%2A> der Schaltfläche auf (0.5, 0.5). Dadurch erfolgt die Drehung um den Mittelpunkt der Schaltfläche, nicht um die obere linke Ecke.  
  
 In der folgenden Abbildung wird das Transformationsergebnis für das folgende Beispiel angezeigt.  
  
 ![Eine um ihren Mittelpunkt transformierte Schaltfläche](./media/graphicsmm-rendertransformrelativecenter.png "Graphicsmm_RenderTransformRelativeCenter")  
Eine Drehung um 45 Grad unter Verwendung der RenderTransform-Eigenschaft mit einem RenderTransformOrigin von (0.5, 0.5)  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Weitere Informationen zum Transformieren von <xref:System.Windows.FrameworkElement> Objekten finden Sie die [Übersicht über Transformationen](transforms-overview.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.Transform>
- [Übersicht über Transformationen](transforms-overview.md)
- [Themen zu Vorgehensweisen](transformations-how-to-topics.md)
