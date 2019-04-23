---
title: 'Vorgehensweise: Drehen eines Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: d1c4700a5dc8f6ed99043552999d8f014116da8f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189642"
---
# <a name="how-to-rotate-an-object"></a>Vorgehensweise: Drehen eines Objekts
Dieses Beispiel zeigt, wie ein Objekt gedreht wird. Das Beispiel erstellt zuerst eine <xref:System.Windows.Media.RotateTransform> und gibt dann die <xref:System.Windows.Media.RotateTransform.Angle%2A> in Grad.  
  
 Im folgende Beispiel wird eine <xref:System.Windows.Shapes.Polyline> -Objekt um 45 Grad um seine linke obere Ecke.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 Die <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> Eigenschaften der <xref:System.Windows.Media.RotateTransform> Geben Sie den an den das Objekt gedreht wird. Dieser Mittelpunkt wird im Koordinatenraum des Elements ausgedrückt, das transformiert wird. Standardmäßig wird die Drehung um den Punkt (0,0), die obere linke Ecke des zu transformierenden Objekts, vorgenommen.  
  
 Im nächsten Beispiel wird eine <xref:System.Windows.Shapes.Polyline> Objekt im Uhrzeigersinn um 45 Grad der Punkt (25,50 gedreht).  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 Die folgende Abbildung zeigt die Ergebnisse der Anwendung eine <xref:System.Windows.Media.Transform> auf die beiden Objekte.  
  
 ![45-Grad-Drehungen mit unterschiedlichen Mittelpunkten](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
Zwei Objekte, die um unterschiedliche Drehpunkte um 45 Grad gedreht werden  
  
 Die <xref:System.Windows.Shapes.Polyline> in den vorherigen Beispielen ist ein <xref:System.Windows.UIElement>. Beim Anwenden von eine <xref:System.Windows.Media.Transform> auf der <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft eine <xref:System.Windows.UIElement>, können Sie die <xref:System.Windows.UIElement.RenderTransformOrigin%2A> -Eigenschaft an einen Ursprung für jedes <xref:System.Windows.Media.Transform> , die Sie anwenden, auf das Element. Da die <xref:System.Windows.UIElement.RenderTransformOrigin%2A> -Eigenschaft relative Koordinaten verwendet, können Sie eine Transformation in der Mitte des Elements anwenden, selbst wenn Sie nicht wissen, dass seine Größe. Weitere Informationen und ein Beispiel finden Sie [angeben des Ursprungs einer Transformation mithilfe von relativen Werten](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).  
  
 Das vollständige Beispiel finden Sie im [Beispiel einer 2D-Transformation](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Transform>
- [Übersicht über Transformationen](transforms-overview.md)
- [Themen zu Vorgehensweisen](transformations-how-to-topics.md)
