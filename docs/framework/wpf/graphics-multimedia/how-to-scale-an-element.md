---
title: 'Gewusst wie: Skalieren eines Elements'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d2bff810dc9b44b25db93c8565da27acc4f0ccc3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-scale-an-element"></a>Gewusst wie: Skalieren eines Elements
Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.ScaleTransform> auf ein Element zu skalieren.  
  
 Verwenden der <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> Eigenschaften zum Ändern der Elementgröße durch den Faktor, geben Sie Sie. Angenommen, ein <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Wert von 1,5 streckt das Element auf 150 Prozent der ursprünglichen Breite. Ein <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> Wert von 0,5 verkleinert die Höhe eines Elements um 50 Prozent.  
  
 Verwenden der <xref:System.Windows.Media.ScaleTransform.CenterX%2A> und <xref:System.Windows.Media.ScaleTransform.CenterY%2A> Eigenschaften, um den Punkt anzugeben, die das Zentrum des der Skalierungsvorgang ist. Wird standardmäßig ein <xref:System.Windows.Media.ScaleTransform> wird an dem Punkt (0,0), entspricht der linken oberen Ecke des Rechtecks zentriert. Dies wirkt sich das Element verschoben wird und somit größer, angezeigt werden, da beim Anwenden einer <xref:System.Windows.Media.Transform>, Sie ändern die Koordinatenbereich, in dem sich das Objekt befindet.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.ScaleTransform> die Größe des ein 50 x 50 verdoppeln <xref:System.Windows.Shapes.Rectangle>. Die <xref:System.Windows.Media.ScaleTransform> hat den Wert 0 (Standard) für beide <xref:System.Windows.Media.ScaleTransform.CenterX%2A> und <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[transformsSample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 Legen Sie in der Regel <xref:System.Windows.Media.ScaleTransform.CenterX%2A> und <xref:System.Windows.Media.ScaleTransform.CenterY%2A> in die Mitte des Objekts, das skaliert wird: (<xref:System.Windows.FrameworkElement.Width%2A>/2,  <xref:System.Windows.FrameworkElement.Height%2A> /2).  
  
 Das folgende Beispiel zeigt eine andere <xref:System.Windows.Shapes.Rectangle> verdoppelt, die Größe; allerdings dies <xref:System.Windows.Media.ScaleTransform> hat den Wert 25 für beide <xref:System.Windows.Media.ScaleTransform.CenterX%2A> und <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, entspricht der Mitte des Rechtecks.  
  
 [!code-xaml[transformsSample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 Die folgende Abbildung zeigt den Unterschied zwischen den beiden <xref:System.Windows.Media.ScaleTransform> Vorgänge. Die gepunktete Linie stellt die Größe und die Position des Rechtecks vor der Skalierung dar.  
  
 ![2-fach-Skalierung mit unterschiedlichen Mittelpunkten](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.gif "Wcpsdk_graphicsmm_scalecenter")  
Zwei ScaleTransform-Vorgänge mit identischen ScaleX- und ScaleY-Werten aber unterschiedlichen Mittelpunkten  
  
 Das vollständige Beispiel finden Sie im [Beispiel einer 2D-Transformation](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
