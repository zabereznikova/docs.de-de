---
title: 'Gewusst wie: Drehen eines Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: e17d3b7b9986b477df198480129edaf4c139c6bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112062"
---
# <a name="how-to-rotate-an-object"></a>Gewusst wie: Drehen eines Objekts
Dieses Beispiel zeigt, wie ein Objekt gedreht wird. Das Beispiel erstellt <xref:System.Windows.Media.RotateTransform> zuerst eine <xref:System.Windows.Media.RotateTransform.Angle%2A> und gibt dann dessen in Grad an.  
  
 Im folgenden Beispiel <xref:System.Windows.Shapes.Polyline> wird ein Objekt um 45 Grad um seine linke obere Ecke gedreht.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 Die <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> und Eigenschaften <xref:System.Windows.Media.RotateTransform> des geben den Punkt an, um den das Objekt gedreht wird. Dieser Mittelpunkt wird im Koordinatenraum des Elements ausgedrückt, das transformiert wird. Standardmäßig wird die Drehung um den Punkt (0,0), die obere linke Ecke des zu transformierenden Objekts, vorgenommen.  
  
 Im nächsten Beispiel <xref:System.Windows.Shapes.Polyline> wird ein Objekt im Uhrzeigersinn um 45 Grad um den Punkt (25,50) gedreht.  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 Die folgende Abbildung zeigt die <xref:System.Windows.Media.Transform> Ergebnisse der Anwendung eines auf die beiden Objekte.  
  
 ![45-Grad-Drehungen mit unterschiedlichen Mittelpunkten](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
Zwei Objekte, die um unterschiedliche Drehpunkte um 45 Grad gedreht werden  
  
 Die <xref:System.Windows.Shapes.Polyline> in den vorherigen <xref:System.Windows.UIElement>Beispielen ist eine . Wenn Sie <xref:System.Windows.Media.Transform> eine <xref:System.Windows.UIElement.RenderTransform%2A> auf die <xref:System.Windows.UIElement>Eigenschaft eines <xref:System.Windows.UIElement.RenderTransformOrigin%2A> anwenden, können Sie <xref:System.Windows.Media.Transform> die Eigenschaft verwenden, um einen Ursprung für jeden anzugeben, den Sie auf das Element anwenden. Da <xref:System.Windows.UIElement.RenderTransformOrigin%2A> die Eigenschaft relative Koordinaten verwendet, können Sie eine Transformation auf die Mitte des Elements anwenden, auch wenn Sie ihre Größe nicht kennen. Weitere Informationen und ein Beispiel finden Sie unter [Angeben des Ursprungs einer Transformation mithilfe relativer Werte](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).  
  
 Das vollständige Beispiel finden Sie unter [2D-Transformationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Transform>
- [Übersicht über Transformationen](transforms-overview.md)
- [How-to-Themen](transformations-how-to-topics.md)
