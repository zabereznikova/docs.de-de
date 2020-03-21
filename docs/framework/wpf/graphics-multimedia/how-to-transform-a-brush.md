---
title: 'Gewusst wie: Transformieren eines Pinsels'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: b4484e2fc1ae3e969b02b1d8f3ae4ab2a035558e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187338"
---
# <a name="how-to-transform-a-brush"></a><span data-ttu-id="7350c-102">Gewusst wie: Transformieren eines Pinsels</span><span class="sxs-lookup"><span data-stu-id="7350c-102">How to: Transform a Brush</span></span>
<span data-ttu-id="7350c-103">In diesem Beispiel <xref:System.Windows.Media.Brush> wird gezeigt, wie Objekte <xref:System.Windows.Media.Brush.RelativeTransform%2A> <xref:System.Windows.Media.Brush.Transform%2A>mithilfe ihrer beiden Transformationseigenschaften transformiert werden: und .</span><span class="sxs-lookup"><span data-stu-id="7350c-103">This example shows how to transform <xref:System.Windows.Media.Brush> objects by using their two transformation properties: <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A>.</span></span>  
  
 <span data-ttu-id="7350c-104">In den folgenden <xref:System.Windows.Media.RotateTransform> Beispielen wird <xref:System.Windows.Media.ImageBrush> ein verwendet, um den Inhalt eines um 45 Grad zu drehen.</span><span class="sxs-lookup"><span data-stu-id="7350c-104">The following examples use a <xref:System.Windows.Media.RotateTransform> to rotate the content of an <xref:System.Windows.Media.ImageBrush> by 45 degrees.</span></span>  
  
 <span data-ttu-id="7350c-105">Die folgende Abbildung <xref:System.Windows.Media.ImageBrush> zeigt <xref:System.Windows.Media.RotateTransform>die <xref:System.Windows.Media.RotateTransform> ohne a, wobei die auf die <xref:System.Windows.Media.Brush.RelativeTransform%2A> Eigenschaft angewendet und die <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.Media.Brush.Transform%2A> Eigenschaft angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="7350c-105">The following illustration shows the <xref:System.Windows.Media.ImageBrush> without a <xref:System.Windows.Media.RotateTransform>, with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property, and with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.Transform%2A> property.</span></span>  
  
 <span data-ttu-id="7350c-106">![RelativeTransform- und Transform-Pinseleinstellungen](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span><span class="sxs-lookup"><span data-stu-id="7350c-106">![Brush RelativeTransform and Transform settings](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span></span>  
  
## <a name="example"></a><span data-ttu-id="7350c-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7350c-107">Example</span></span>  
 <span data-ttu-id="7350c-108">Das erste Beispiel <xref:System.Windows.Media.RotateTransform> wendet <xref:System.Windows.Media.Brush.RelativeTransform%2A> eine <xref:System.Windows.Media.ImageBrush>auf die Eigenschaft einer an.</span><span class="sxs-lookup"><span data-stu-id="7350c-108">The first example applies a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property of an <xref:System.Windows.Media.ImageBrush>.</span></span> <span data-ttu-id="7350c-109">Die <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> und Eigenschaften <xref:System.Windows.Media.RotateTransform> eines Objekts sind beide auf 0,5 festgelegt, was die relative Koordinate des Mittelpunkts dieses Inhalts ist.</span><span class="sxs-lookup"><span data-stu-id="7350c-109">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of a <xref:System.Windows.Media.RotateTransform> object are both set to 0.5, which is the relative coordinate of the center point of this content.</span></span> <span data-ttu-id="7350c-110">Dadurch dreht sich <xref:System.Windows.Media.ImageBrush> der Inhalt um seine Mitte.</span><span class="sxs-lookup"><span data-stu-id="7350c-110">As a result, the <xref:System.Windows.Media.ImageBrush> content rotates about its center.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 <span data-ttu-id="7350c-111">Das zweite Beispiel <xref:System.Windows.Media.RotateTransform> gilt <xref:System.Windows.Media.ImageBrush>auch für eine ; In diesem Beispiel <xref:System.Windows.Media.Brush.Transform%2A> wird jedoch <xref:System.Windows.Media.Brush.RelativeTransform%2A> die Eigenschaft anstelle der Eigenschaft verwendet.</span><span class="sxs-lookup"><span data-stu-id="7350c-111">The second example also applies a <xref:System.Windows.Media.RotateTransform> to an <xref:System.Windows.Media.ImageBrush>; however, this example uses the <xref:System.Windows.Media.Brush.Transform%2A> property instead of the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property.</span></span>  
  
 <span data-ttu-id="7350c-112">Um den Pinsel um seine Mitte <xref:System.Windows.Media.RotateTransform.CenterX%2A> zu <xref:System.Windows.Media.RotateTransform.CenterY%2A> drehen, <xref:System.Windows.Media.RotateTransform> legt das Beispiel die und die Eigenschaften des Objekts auf absolute Koordinaten fest.</span><span class="sxs-lookup"><span data-stu-id="7350c-112">To rotate the brush about its center, the example sets the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> object to absolute coordinates.</span></span> <span data-ttu-id="7350c-113">Da der Pinsel ein Rechteck mit der Größe 175 mal 90 Pixel zeichnet, liegt der Mittelpunkt des Rechtecks bei (87,5/45).</span><span class="sxs-lookup"><span data-stu-id="7350c-113">Because the brush paints a rectangle that is 175 by 90 pixels, the center point of the rectangle is (87.5, 45).</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 <span data-ttu-id="7350c-114">Eine Beschreibung der <xref:System.Windows.Media.Brush.RelativeTransform%2A> Funktionsweise <xref:System.Windows.Media.Brush.Transform%2A> und der Eigenschaften finden Sie in der [Pinseltransformationsübersicht](brush-transformation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7350c-114">For a description of how the <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A> properties work, see the [Brush Transformation Overview](brush-transformation-overview.md).</span></span>  
  
 <span data-ttu-id="7350c-115">Das vollständige Beispiel finden Sie unter [Beispiel für Pinsel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="7350c-115">For the complete sample, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="7350c-116">Weitere Informationen über Pinsel finden Sie unter [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7350c-116">For more information about brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7350c-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7350c-117">See also</span></span>

- [<span data-ttu-id="7350c-118">Übersicht über Pinseltransformationen</span><span class="sxs-lookup"><span data-stu-id="7350c-118">Brush Transformation Overview</span></span>](brush-transformation-overview.md)
- [<span data-ttu-id="7350c-119">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="7350c-119">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="7350c-120">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="7350c-120">Transforms Overview</span></span>](transforms-overview.md)
