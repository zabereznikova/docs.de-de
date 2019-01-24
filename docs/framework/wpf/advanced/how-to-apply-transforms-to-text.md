---
title: 'Vorgehensweise: Anwenden von Transformationen auf Text'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], rotated text
- typography [WPF], scaled text
- skewed text [WPF]
- typography [WPF], translated text
- typography [WPF], shadowed text
- rotated text [WPF]
- translated text [WPF]
- shadowed text [WPF]
- transforms in text [WPF]
- typography [WPF], transforms
- scaled text [WPF]
- typography [WPF], skewed text
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
ms.openlocfilehash: 7737a2e01ddfe2a639426bbced643d8f78961207
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740543"
---
# <a name="how-to-apply-transforms-to-text"></a><span data-ttu-id="3ddc4-102">Vorgehensweise: Anwenden von Transformationen auf Text</span><span class="sxs-lookup"><span data-stu-id="3ddc4-102">How to: Apply Transforms to Text</span></span>
<span data-ttu-id="3ddc4-103">Transformationen können die Anzeige von Text in Ihrer Anwendung ändern.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-103">Transforms can alter the display of text in your application.</span></span> <span data-ttu-id="3ddc4-104">Die folgenden Beispiele verwenden verschiedene Arten von Renderingtransformationen die Anzeige von Text in beeinflusst eine <xref:System.Windows.Controls.TextBlock> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-104">The following examples use different types of rendering transforms to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ddc4-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ddc4-105">Example</span></span>  
 <span data-ttu-id="3ddc4-106">Das folgende Beispiel zeigt um einen bestimmten Punkt in der zweidimensionalen X-Y-Ebene gedrehten Text.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-106">The following example shows text rotated about a specified point in the two-dimensional x-y plane.</span></span>  
  
 <span data-ttu-id="3ddc4-107">![Gedrehter Text mithilfe einer RotateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext01.jpg "TransformedText01")</span><span class="sxs-lookup"><span data-stu-id="3ddc4-107">![Text rotated using a RotateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext01.jpg "TransformedText01")</span></span>  
<span data-ttu-id="3ddc4-108">Beispiel für um 90 Grad gedrehten Text</span><span class="sxs-lookup"><span data-stu-id="3ddc4-108">Example of text rotated 90 degrees</span></span>  
  
 <span data-ttu-id="3ddc4-109">Im folgenden Codebeispiel wird eine <xref:System.Windows.Media.RotateTransform> um Text zu drehen.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-109">The following code example uses a <xref:System.Windows.Media.RotateTransform> to rotate text.</span></span> <span data-ttu-id="3ddc4-110">Ein <xref:System.Windows.Media.RotateTransform.Angle%2A> -Wert von 90 Dreht das Element um 90 Grad im Uhrzeigersinn.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-110">An <xref:System.Windows.Media.RotateTransform.Angle%2A> value of 90 rotates the element 90 degrees clockwise.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 <span data-ttu-id="3ddc4-111">Das folgende Beispiel zeigt die zweite Textzeile, die um 150 % entlang der X-Achse skaliert ist, und die dritte Textzeile, die um 150 % entlang der Y-Achse skaliert ist.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-111">The following example shows the second line of text scaled by 150% along the x-axis, and the third line of text scaled by 150% along the y-axis.</span></span>  
  
 <span data-ttu-id="3ddc4-112">![Skalierter Text mithilfe einer ScaleTransform skalierter](../../../../docs/framework/wpf/advanced/media/transformedtext02.jpg "TransformedText02")</span><span class="sxs-lookup"><span data-stu-id="3ddc4-112">![Text scaled using a ScaleTransform](../../../../docs/framework/wpf/advanced/media/transformedtext02.jpg "TransformedText02")</span></span>  
<span data-ttu-id="3ddc4-113">Beispiel für skalierten Text</span><span class="sxs-lookup"><span data-stu-id="3ddc4-113">Example of scaled text</span></span>  
  
 <span data-ttu-id="3ddc4-114">Im folgenden Codebeispiel wird eine <xref:System.Windows.Media.ScaleTransform> zum Skalieren von Text aus der ursprünglichen Größe.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-114">The following code example uses a <xref:System.Windows.Media.ScaleTransform> to scale text from its original size.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  <span data-ttu-id="3ddc4-115">Das Skalieren von Text ist nicht identisch mit der Erhöhung des Schriftgrads des Texts.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-115">Scaling text is not the same as increasing the font size of text.</span></span> <span data-ttu-id="3ddc4-116">Schriftgrade werden unabhängig voneinander berechnet, um die beste Lösung in unterschiedlichen Größen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-116">Font sizes are calculated independently of each other in order to provide the best resolution at different sizes.</span></span> <span data-ttu-id="3ddc4-117">Skalierter Text behält andererseits die Proportionen der ursprünglichen Textgröße bei.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-117">Scaled text, on the other hand, preserves the proportions of the original-sized text.</span></span>  
  
 <span data-ttu-id="3ddc4-118">Das folgende Beispiel zeigt einen entlang der X-Achse geneigten Text.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-118">The following example shows text skewed along the x-axis.</span></span>  
  
 <span data-ttu-id="3ddc4-119">![Geneigter Text mithilfe einer SkewTransform](../../../../docs/framework/wpf/advanced/media/transformedtext03.jpg "TransformedText03")</span><span class="sxs-lookup"><span data-stu-id="3ddc4-119">![Text skewed using a SkewTransform](../../../../docs/framework/wpf/advanced/media/transformedtext03.jpg "TransformedText03")</span></span>  
<span data-ttu-id="3ddc4-120">Beispiel für verzerrten Text</span><span class="sxs-lookup"><span data-stu-id="3ddc4-120">Example of skewed text</span></span>  
  
 <span data-ttu-id="3ddc4-121">Im folgenden Codebeispiel wird eine <xref:System.Windows.Media.SkewTransform> um Text zu neigen.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-121">The following code example uses a <xref:System.Windows.Media.SkewTransform> to skew text.</span></span> <span data-ttu-id="3ddc4-122">Eine Neigung ist eine Transformation, die den Koordinatenraum auf ungleichmäßige Art ausdehnt.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-122">A skew, also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="3ddc4-123">In diesem Beispiel werden die zwei Textzeichenfolgen um -30 Grad und 30 Grad entlang der X-Koordinate geneigt.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-123">In this example, the two text strings are skewed -30° and 30° along the x-coordinate.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 <span data-ttu-id="3ddc4-124">Das folgende Beispiel zeigt Text, der entlang der X- und Y-Achse übersetzt oder verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-124">The following example shows text translated, or moved, along the x- and y-axis.</span></span>  
  
 <span data-ttu-id="3ddc4-125">![Textversatz mithilfe einer TranslateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext04.jpg "TransformedText04")</span><span class="sxs-lookup"><span data-stu-id="3ddc4-125">![Text offset using a TranslateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext04.jpg "TransformedText04")</span></span>  
<span data-ttu-id="3ddc4-126">Beispiel für übersetzten Text</span><span class="sxs-lookup"><span data-stu-id="3ddc4-126">Example of translated text</span></span>  
  
 <span data-ttu-id="3ddc4-127">Im folgenden Codebeispiel wird eine <xref:System.Windows.Media.TranslateTransform> um Text zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-127">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="3ddc4-128">In diesem Beispiel erstellt eine geringfügig versetzte Kopie des Textes hinter dem primären Text einen Schatteneffekt.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-128">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  <span data-ttu-id="3ddc4-129">Die <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> bietet einen umfangreichen Satz von Funktionen für das Bereitstellen von Schatteneffekten.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-129">The <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> provides a rich set of features for providing shadow effects.</span></span> <span data-ttu-id="3ddc4-130">Weitere Informationen finden Sie unter [Erstellen von Text mit einem Schatten](../../../../docs/framework/wpf/advanced/how-to-create-text-with-a-shadow.md).</span><span class="sxs-lookup"><span data-stu-id="3ddc4-130">For more information, see [Create Text with a Shadow](../../../../docs/framework/wpf/advanced/how-to-create-text-with-a-shadow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ddc4-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ddc4-131">See also</span></span>
- [<span data-ttu-id="3ddc4-132">Anwenden von Animationen auf Text</span><span class="sxs-lookup"><span data-stu-id="3ddc4-132">Apply Animations to Text</span></span>](../../../../docs/framework/wpf/advanced/how-to-apply-animations-to-text.md)
