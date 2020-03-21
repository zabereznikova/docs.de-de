---
title: 'Gewusst wie: Skalieren eines Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 34d954f68747be9eedc0ef71634e0c18b411d260
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112049"
---
# <a name="how-to-scale-an-element"></a>Gewusst wie: Skalieren eines Elements
In diesem Beispiel wird <xref:System.Windows.Media.ScaleTransform> gezeigt, wie ein Element skaliert wird.  
  
 Verwenden <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Sie <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> die und Eigenschaften, um die Größe des Elements um den angegebenen Faktor zu ändern. Ein <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Wert von 1,5 dehnt das Element beispielsweise auf 150 Prozent seiner ursprünglichen Breite aus. Bei <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> einem Wert von 0,5 wird die Höhe eines Elements um 50 Prozent verkleinert.  
  
 Verwenden <xref:System.Windows.Media.ScaleTransform.CenterX%2A> Sie <xref:System.Windows.Media.ScaleTransform.CenterY%2A> die und Eigenschaften, um den Punkt anzugeben, der den Mittelpunkt des Skalierungsvorgangs ist. Standardmäßig wird <xref:System.Windows.Media.ScaleTransform> a am Punkt (0,0) zentriert, der der oberen linken Ecke des Rechtecks entspricht. Dies hat den Effekt, dass das Element bewegt und auch <xref:System.Windows.Media.Transform>größer angezeigt wird, da Sie beim Anwenden eines den Koordinatenraum ändern, in dem sich das Objekt befindet.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.ScaleTransform> wird eine verwendet, um die Größe <xref:System.Windows.Shapes.Rectangle>eines 50-mal-50 zu verdoppeln. Der <xref:System.Windows.Media.ScaleTransform> hat den Wert 0 (Standardwert) für beide <xref:System.Windows.Media.ScaleTransform.CenterX%2A> und <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 In der <xref:System.Windows.Media.ScaleTransform.CenterX%2A> Regel <xref:System.Windows.Media.ScaleTransform.CenterY%2A> legen Sie und auf die Mitte<xref:System.Windows.FrameworkElement.Width%2A>des <xref:System.Windows.FrameworkElement.Height%2A>Objekts, das skaliert wird: ( /2, /2).  
  
 Das folgende Beispiel <xref:System.Windows.Shapes.Rectangle> zeigt ein anderes, das doppelt so groß ist. Dies <xref:System.Windows.Media.ScaleTransform> hat jedoch einen Wert <xref:System.Windows.Media.ScaleTransform.CenterX%2A> von <xref:System.Windows.Media.ScaleTransform.CenterY%2A>25 für beide und , was der Mitte des Rechtecks entspricht.  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 Die folgende Abbildung zeigt den <xref:System.Windows.Media.ScaleTransform> Unterschied zwischen den beiden Vorgängen. Die gepunktete Linie stellt die Größe und die Position des Rechtecks vor der Skalierung dar.  
  
 ![2-fach-Skalierung mit unterschiedlichen Mittelpunkten](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")  
Zwei ScaleTransform-Vorgänge mit identischen ScaleX- und ScaleY-Werten aber unterschiedlichen Mittelpunkten  
  
 Das vollständige Beispiel finden Sie unter [2D-Transformationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [Übersicht über Transformationen](transforms-overview.md)
- [How-to-Themen](transformations-how-to-topics.md)
