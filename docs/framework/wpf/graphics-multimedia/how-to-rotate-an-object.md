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
# <a name="how-to-rotate-an-object"></a><span data-ttu-id="4e4c1-102">Vorgehensweise: Drehen eines Objekts</span><span class="sxs-lookup"><span data-stu-id="4e4c1-102">How to: Rotate an Object</span></span>
<span data-ttu-id="4e4c1-103">Dieses Beispiel zeigt, wie ein Objekt gedreht wird.</span><span class="sxs-lookup"><span data-stu-id="4e4c1-103">This example shows how to rotate an object.</span></span> <span data-ttu-id="4e4c1-104">Das Beispiel erstellt zuerst eine <xref:System.Windows.Media.RotateTransform> und gibt dann die <xref:System.Windows.Media.RotateTransform.Angle%2A> in Grad.</span><span class="sxs-lookup"><span data-stu-id="4e4c1-104">The example first creates a <xref:System.Windows.Media.RotateTransform> and then specifies its <xref:System.Windows.Media.RotateTransform.Angle%2A> in degrees.</span></span>  
  
 <span data-ttu-id="4e4c1-105">Im folgende Beispiel wird eine <xref:System.Windows.Shapes.Polyline> -Objekt um 45 Grad um seine linke obere Ecke.</span><span class="sxs-lookup"><span data-stu-id="4e4c1-105">The following example rotates a <xref:System.Windows.Shapes.Polyline> object 45 degrees about its upper-left corner.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e4c1-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4e4c1-106">Example</span></span>  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <span data-ttu-id="4e4c1-107">Die <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> Eigenschaften der <xref:System.Windows.Media.RotateTransform> Geben Sie den an den das Objekt gedreht wird.</span><span class="sxs-lookup"><span data-stu-id="4e4c1-107">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> specify the point about which the object is rotated.</span></span> <span data-ttu-id="4e4c1-108">Dieser Mittelpunkt wird im Koordinatenraum des Elements ausgedrückt, das transformiert wird.</span><span class="sxs-lookup"><span data-stu-id="4e4c1-108">This center point is expressed in the coordinate space of the element that is transformed.</span></span> <span data-ttu-id="4e4c1-109">Standardmäßig wird die Drehung um den Punkt (0,0), die obere linke Ecke des zu transformierenden Objekts, vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="4e4c1-109">By default, the rotation is applied to (0,0), which is the upper-left corner of the object to transform.</span></span>  
  
 <span data-ttu-id="4e4c1-110">Im nächsten Beispiel wird eine <xref:System.Windows.Shapes.Polyline> Objekt im Uhrzeigersinn um 45 Grad der Punkt (25,50 gedreht).</span><span class="sxs-lookup"><span data-stu-id="4e4c1-110">The next example rotates a <xref:System.Windows.Shapes.Polyline> object clockwise 45 degrees about the point (25,50).</span></span>  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 <span data-ttu-id="4e4c1-111">Die folgende Abbildung zeigt die Ergebnisse der Anwendung eine <xref:System.Windows.Media.Transform> auf die beiden Objekte.</span><span class="sxs-lookup"><span data-stu-id="4e4c1-111">The following illustration shows the results of applying a <xref:System.Windows.Media.Transform> to the two objects.</span></span>  
  
 <span data-ttu-id="4e4c1-112">![45-Grad-Drehungen mit unterschiedlichen Mittelpunkten](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="4e4c1-112">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
<span data-ttu-id="4e4c1-113">Zwei Objekte, die um unterschiedliche Drehpunkte um 45 Grad gedreht werden</span><span class="sxs-lookup"><span data-stu-id="4e4c1-113">Two objects that rotate 45 degrees from different rotational centers</span></span>  
  
 <span data-ttu-id="4e4c1-114">Die <xref:System.Windows.Shapes.Polyline> in den vorherigen Beispielen ist ein <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="4e4c1-114">The <xref:System.Windows.Shapes.Polyline> in the previous examples is a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="4e4c1-115">Beim Anwenden von eine <xref:System.Windows.Media.Transform> auf der <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft eine <xref:System.Windows.UIElement>, können Sie die <xref:System.Windows.UIElement.RenderTransformOrigin%2A> -Eigenschaft an einen Ursprung für jedes <xref:System.Windows.Media.Transform> , die Sie anwenden, auf das Element.</span><span class="sxs-lookup"><span data-stu-id="4e4c1-115">When you apply a <xref:System.Windows.Media.Transform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a <xref:System.Windows.UIElement>, you can use the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to specify an origin for every <xref:System.Windows.Media.Transform> that you apply to the element.</span></span> <span data-ttu-id="4e4c1-116">Da die <xref:System.Windows.UIElement.RenderTransformOrigin%2A> -Eigenschaft relative Koordinaten verwendet, können Sie eine Transformation in der Mitte des Elements anwenden, selbst wenn Sie nicht wissen, dass seine Größe.</span><span class="sxs-lookup"><span data-stu-id="4e4c1-116">Because the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property uses relative coordinates, you can apply a transformation to the center of the element even if you do not know its size.</span></span> <span data-ttu-id="4e4c1-117">Weitere Informationen und ein Beispiel finden Sie [angeben des Ursprungs einer Transformation mithilfe von relativen Werten](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span><span class="sxs-lookup"><span data-stu-id="4e4c1-117">For more information and for an example, see [Specify the Origin of a Transform by Using Relative Values](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span></span>  
  
 <span data-ttu-id="4e4c1-118">Das vollständige Beispiel finden Sie im [Beispiel einer 2D-Transformation](https://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="4e4c1-118">For the complete sample, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e4c1-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e4c1-119">See also</span></span>

- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="4e4c1-120">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="4e4c1-120">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="4e4c1-121">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="4e4c1-121">How-to Topics</span></span>](transformations-how-to-topics.md)
