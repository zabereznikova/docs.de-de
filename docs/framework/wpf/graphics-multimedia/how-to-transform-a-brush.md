---
title: 'Vorgehensweise: Transformieren eines Pinsels'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: 990c82b4844ce3ca7f5b553b180280b6b37496ca
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373763"
---
# <a name="how-to-transform-a-brush"></a><span data-ttu-id="057be-102">Vorgehensweise: Transformieren eines Pinsels</span><span class="sxs-lookup"><span data-stu-id="057be-102">How to: Transform a Brush</span></span>
<span data-ttu-id="057be-103">Dieses Beispiel zeigt, wie Sie transformieren <xref:System.Windows.Media.Brush> Objekte mithilfe von zwei Transformationseigenschaften: <xref:System.Windows.Media.Brush.RelativeTransform%2A> und <xref:System.Windows.Media.Brush.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="057be-103">This example shows how to transform <xref:System.Windows.Media.Brush> objects by using their two transformation properties: <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A>.</span></span>  
  
 <span data-ttu-id="057be-104">Die folgenden Beispiele verwenden eine <xref:System.Windows.Media.RotateTransform> so drehen den Inhalt des ein <xref:System.Windows.Media.ImageBrush> um 45 Grad um.</span><span class="sxs-lookup"><span data-stu-id="057be-104">The following examples use a <xref:System.Windows.Media.RotateTransform> to rotate the content of an <xref:System.Windows.Media.ImageBrush> by 45 degrees.</span></span>  
  
 <span data-ttu-id="057be-105">Die folgende Abbildung zeigt die <xref:System.Windows.Media.ImageBrush> ohne eine <xref:System.Windows.Media.RotateTransform>, mit der <xref:System.Windows.Media.RotateTransform> angewendet der <xref:System.Windows.Media.Brush.RelativeTransform%2A> -Eigenschaft, und mit der <xref:System.Windows.Media.RotateTransform> angewendet der <xref:System.Windows.Media.Brush.Transform%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="057be-105">The following illustration shows the <xref:System.Windows.Media.ImageBrush> without a <xref:System.Windows.Media.RotateTransform>, with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property, and with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.Transform%2A> property.</span></span>  
  
 <span data-ttu-id="057be-106">![RelativeTransform- und Transform-Pinseleinstellungen](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "Wcpsdk_graphicsmm_transformandrelativetransform")</span><span class="sxs-lookup"><span data-stu-id="057be-106">![Brush RelativeTransform and Transform settings](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span></span>  
  
## <a name="example"></a><span data-ttu-id="057be-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="057be-107">Example</span></span>  
 <span data-ttu-id="057be-108">Im ersten Beispiel wird eine <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.Media.Brush.RelativeTransform%2A> Eigenschaft eine <xref:System.Windows.Media.ImageBrush>.</span><span class="sxs-lookup"><span data-stu-id="057be-108">The first example applies a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property of an <xref:System.Windows.Media.ImageBrush>.</span></span> <span data-ttu-id="057be-109">Die <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> Eigenschaften eine <xref:System.Windows.Media.RotateTransform> Objekt beide auf 0,5, d.h. die relative des Mittelpunkts dieser Inhalte Koordinate festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="057be-109">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of a <xref:System.Windows.Media.RotateTransform> object are both set to 0.5, which is the relative coordinate of the center point of this content.</span></span> <span data-ttu-id="057be-110">Daher die <xref:System.Windows.Media.ImageBrush> Inhalt dreht sich seinen Mittelpunkt.</span><span class="sxs-lookup"><span data-stu-id="057be-110">As a result, the <xref:System.Windows.Media.ImageBrush> content rotates about its center.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 <span data-ttu-id="057be-111">Im zweite Beispiel gilt auch für eine <xref:System.Windows.Media.RotateTransform> auf eine <xref:System.Windows.Media.ImageBrush>, aber dieses Beispiel verwendet die <xref:System.Windows.Media.Brush.Transform%2A> -Eigenschaft anstelle von der <xref:System.Windows.Media.Brush.RelativeTransform%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="057be-111">The second example also applies a <xref:System.Windows.Media.RotateTransform> to an <xref:System.Windows.Media.ImageBrush>; however, this example uses the <xref:System.Windows.Media.Brush.Transform%2A> property instead of the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property.</span></span>  
  
 <span data-ttu-id="057be-112">Um den Pinsel um seinen Mittelpunkt zu drehen, im Beispiel wird die <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> Eigenschaften der <xref:System.Windows.Media.RotateTransform> -Objekts auf absolute Koordinaten.</span><span class="sxs-lookup"><span data-stu-id="057be-112">To rotate the brush about its center, the example sets the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> object to absolute coordinates.</span></span> <span data-ttu-id="057be-113">Da der Pinsel ein Rechteck mit der Größe 175 mal 90 Pixel zeichnet, liegt der Mittelpunkt des Rechtecks bei (87,5/45).</span><span class="sxs-lookup"><span data-stu-id="057be-113">Because the brush paints a rectangle that is 175 by 90 pixels, the center point of the rectangle is (87.5, 45).</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 <span data-ttu-id="057be-114">Eine Beschreibung dafür, wie die <xref:System.Windows.Media.Brush.RelativeTransform%2A> und <xref:System.Windows.Media.Brush.Transform%2A> Eigenschaften arbeiten, finden Sie unter den [Übersicht über Pinseltransformationen](brush-transformation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="057be-114">For a description of how the <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A> properties work, see the [Brush Transformation Overview](brush-transformation-overview.md).</span></span>  
  
 <span data-ttu-id="057be-115">Das vollständige Beispiel finden Sie unter [Beispiel für Pinsel](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="057be-115">For the complete sample, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="057be-116">Weitere Informationen über Pinsel finden Sie unter [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="057be-116">For more information about brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="057be-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="057be-117">See also</span></span>
- [<span data-ttu-id="057be-118">Übersicht über Pinseltransformationen</span><span class="sxs-lookup"><span data-stu-id="057be-118">Brush Transformation Overview</span></span>](brush-transformation-overview.md)
- [<span data-ttu-id="057be-119">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="057be-119">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="057be-120">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="057be-120">Transforms Overview</span></span>](transforms-overview.md)
