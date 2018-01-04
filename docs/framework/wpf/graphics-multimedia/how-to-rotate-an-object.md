---
title: 'Gewusst wie: Drehen eines Objekts'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b356ef1782ec5bba4f7288644a0802f029456bbf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-rotate-an-object"></a>Gewusst wie: Drehen eines Objekts
Dieses Beispiel zeigt, wie ein Objekt gedreht wird. Das Beispiel erstellt zuerst eine <xref:System.Windows.Media.RotateTransform> und legt dann die <xref:System.Windows.Media.RotateTransform.Angle%2A> in Grad.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Shapes.Polyline> -Objekt um 45 Grad, zu der oberen linken Ecke.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 Die <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> Eigenschaften der <xref:System.Windows.Media.RotateTransform> angeben des Zeitpunkts, zu dem das Objekt gedreht wird. Dieser Mittelpunkt wird im Koordinatenraum des Elements ausgedrückt, das transformiert wird. Standardmäßig wird die Drehung um den Punkt (0,0), die obere linke Ecke des zu transformierenden Objekts, vorgenommen.  
  
 Im nächsten Beispiel wird eine <xref:System.Windows.Shapes.Polyline> Objekt im Uhrzeigersinn um 45 Grad den Punkt (25; 50).  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 Die folgende Abbildung zeigt die Ergebnisse des Anwendens eine <xref:System.Windows.Media.Transform> auf die beiden Objekte.  
  
 ![45-Grad-Drehungen mit unterschiedlichen Mittelpunkten](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
Zwei Objekte, die um unterschiedliche Drehpunkte um 45 Grad gedreht werden  
  
 Die <xref:System.Windows.Shapes.Polyline> in den vorherigen Beispielen wird eine <xref:System.Windows.UIElement>. Beim Anwenden von eine <xref:System.Windows.Media.Transform> auf die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft eine <xref:System.Windows.UIElement>, können Sie die <xref:System.Windows.UIElement.RenderTransformOrigin%2A> -Eigenschaft an einen Ursprung für jedes <xref:System.Windows.Media.Transform> , die Sie auf das Element angewendet. Da die <xref:System.Windows.UIElement.RenderTransformOrigin%2A> Eigenschaft relative Koordinaten verwendet, können Sie eine Transformation in der Mitte des Elements anwenden, selbst wenn Sie nicht wissen, dass seine Größe. Weitere Informationen und ein Beispiel finden Sie unter [Geben Sie den Ursprung einer Transformation vom mit relativen Werten](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).  
  
 Das vollständige Beispiel finden Sie im [Beispiel einer 2D-Transformation](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Transform>  
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
