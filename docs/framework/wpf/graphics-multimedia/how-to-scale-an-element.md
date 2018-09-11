---
title: 'Gewusst wie: Skalieren eines Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 44c638b58d828e5beb0b9de5c7bb0b67c8e82d87
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "44366019"
---
# <a name="how-to-scale-an-element"></a>Gewusst wie: Skalieren eines Elements
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.ScaleTransform> ein Element skalieren.  
  
 Verwenden der <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> Eigenschaften zum Ändern der Größe des Elements durch der Faktor für die Sie angeben. Z. B. eine <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Wert von 1,5 wird das Element auf 150 Prozent der ursprünglichen Breite gestreckt. Ein <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> Wert von 0,5 verringert sich die Höhe eines Elements um 50 Prozent.  
  
 Verwenden der <xref:System.Windows.Media.ScaleTransform.CenterX%2A> und <xref:System.Windows.Media.ScaleTransform.CenterY%2A> Eigenschaften, die den Punkt angeben, die den Mittelpunkt des skalierungsvorgangs. Standardmäßig eine <xref:System.Windows.Media.ScaleTransform> basiert, an dem Punkt (0,0), das die linke obere Ecke des Rechtecks entspricht. Dies wirkt sich das Element verschoben wird und er größer angezeigt werden, weil beim Anwenden einer <xref:System.Windows.Media.Transform>, Sie ändern den Koordinatenbereich, in dem sich das Objekt befindet.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.ScaleTransform> verdoppeln Sie die Größe des eine 50 x 50 <xref:System.Windows.Shapes.Rectangle>. Die <xref:System.Windows.Media.ScaleTransform> hat den Wert 0 (Standard) für beide <xref:System.Windows.Media.ScaleTransform.CenterX%2A> und <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[transformsSample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 Legen Sie in der Regel <xref:System.Windows.Media.ScaleTransform.CenterX%2A> und <xref:System.Windows.Media.ScaleTransform.CenterY%2A> in der Mitte des Objekts, das skaliert wird: (<xref:System.Windows.FrameworkElement.Width%2A>/2,  <xref:System.Windows.FrameworkElement.Height%2A> /2).  
  
 Das folgende Beispiel zeigt eine andere <xref:System.Windows.Shapes.Rectangle> , Größe verdoppelt wird jedoch dadurch <xref:System.Windows.Media.ScaleTransform> hat den Wert 25 für beide <xref:System.Windows.Media.ScaleTransform.CenterX%2A> und <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, in der Mitte des Rechtecks entspricht.  
  
 [!code-xaml[transformsSample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 Die folgende Abbildung zeigt den Unterschied zwischen den beiden <xref:System.Windows.Media.ScaleTransform> Vorgänge. Die gepunktete Linie stellt die Größe und die Position des Rechtecks vor der Skalierung dar.  
  
 ![2-fach-Skalierung mit unterschiedlichen Mittelpunkten](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.gif "Wcpsdk_graphicsmm_scalecenter")  
Zwei ScaleTransform-Vorgänge mit identischen ScaleX- und ScaleY-Werten aber unterschiedlichen Mittelpunkten  
  
 Das vollständige Beispiel finden Sie im [Beispiel einer 2D-Transformation](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
