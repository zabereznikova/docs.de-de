---
title: 'Gewusst wie: Anwenden von Transformationen auf Text'
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
ms.openlocfilehash: 867f39e3df8493014d8601530e91310c3bbbeeb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141613"
---
# <a name="how-to-apply-transforms-to-text"></a><span data-ttu-id="3ec1e-102">Gewusst wie: Anwenden von Transformationen auf Text</span><span class="sxs-lookup"><span data-stu-id="3ec1e-102">How to: Apply Transforms to Text</span></span>
<span data-ttu-id="3ec1e-103">Transformationen können die Anzeige von Text in Ihrer Anwendung ändern.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-103">Transforms can alter the display of text in your application.</span></span> <span data-ttu-id="3ec1e-104">In den folgenden Beispielen werden verschiedene Arten von Rendering-Transformationen verwendet, um die Anzeige von Text in einem <xref:System.Windows.Controls.TextBlock> Steuerelement zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-104">The following examples use different types of rendering transforms to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ec1e-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ec1e-105">Example</span></span>  
 <span data-ttu-id="3ec1e-106">Das folgende Beispiel zeigt um einen bestimmten Punkt in der zweidimensionalen X-Y-Ebene gedrehten Text.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-106">The following example shows text rotated about a specified point in the two-dimensional x-y plane.</span></span>  
  
 ![Gedrehter Text mithilfe einer RotateTransform](./media/how-to-apply-transforms-to-text/text-rotated-ninety-degrees.jpg)  
  
 <span data-ttu-id="3ec1e-108">Im folgenden Codebeispiel <xref:System.Windows.Media.RotateTransform> wird ein zum Drehen von Text verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-108">The following code example uses a <xref:System.Windows.Media.RotateTransform> to rotate text.</span></span> <span data-ttu-id="3ec1e-109">Bei <xref:System.Windows.Media.RotateTransform.Angle%2A> einem Wert von 90 wird das Element um 90 Grad im Uhrzeigersinn gedreht.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-109">An <xref:System.Windows.Media.RotateTransform.Angle%2A> value of 90 rotates the element 90 degrees clockwise.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 <span data-ttu-id="3ec1e-110">Das folgende Beispiel zeigt die zweite Textzeile, die um 150 % entlang der X-Achse skaliert ist, und die dritte Textzeile, die um 150 % entlang der Y-Achse skaliert ist.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-110">The following example shows the second line of text scaled by 150% along the x-axis, and the third line of text scaled by 150% along the y-axis.</span></span>  
  
 ![Skalierter Text mithilfe einer ScaleTransform](./media/how-to-apply-transforms-to-text/scaled-text-scaletransform.jpg)
  
 <span data-ttu-id="3ec1e-112">Im folgenden Codebeispiel <xref:System.Windows.Media.ScaleTransform> wird ein verwendet, um Text von seiner ursprünglichen Größe zu skalieren.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-112">The following code example uses a <xref:System.Windows.Media.ScaleTransform> to scale text from its original size.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
> <span data-ttu-id="3ec1e-113">Das Skalieren von Text ist nicht identisch mit der Erhöhung des Schriftgrads des Texts.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-113">Scaling text is not the same as increasing the font size of text.</span></span> <span data-ttu-id="3ec1e-114">Schriftgrade werden unabhängig voneinander berechnet, um die beste Lösung in unterschiedlichen Größen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-114">Font sizes are calculated independently of each other in order to provide the best resolution at different sizes.</span></span> <span data-ttu-id="3ec1e-115">Skalierter Text behält andererseits die Proportionen der ursprünglichen Textgröße bei.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-115">Scaled text, on the other hand, preserves the proportions of the original-sized text.</span></span>  
  
 <span data-ttu-id="3ec1e-116">Das folgende Beispiel zeigt einen entlang der X-Achse geneigten Text.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-116">The following example shows text skewed along the x-axis.</span></span>  
  
 ![Geneigter Text mithilfe einer SkewTransform](./media/how-to-apply-transforms-to-text/skewed-transformed-text.jpg)

 <span data-ttu-id="3ec1e-118">Im folgenden Codebeispiel <xref:System.Windows.Media.SkewTransform> wird ein zum Verzerren von Text verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-118">The following code example uses a <xref:System.Windows.Media.SkewTransform> to skew text.</span></span> <span data-ttu-id="3ec1e-119">Eine Neigung ist eine Transformation, die den Koordinatenraum auf ungleichmäßige Art ausdehnt.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-119">A skew, also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="3ec1e-120">In diesem Beispiel werden die zwei Textzeichenfolgen um -30 Grad und 30 Grad entlang der X-Koordinate geneigt.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-120">In this example, the two text strings are skewed -30° and 30° along the x-coordinate.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 <span data-ttu-id="3ec1e-121">Das folgende Beispiel zeigt Text, der entlang der X- und Y-Achse übersetzt oder verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-121">The following example shows text translated, or moved, along the x- and y-axis.</span></span>  
  
 ![Textversatz mithilfe einer TranslateTransform](./media/how-to-apply-transforms-to-text/transformed-text-x-y-axis.jpg)
  
 <span data-ttu-id="3ec1e-123">Im folgenden Codebeispiel <xref:System.Windows.Media.TranslateTransform> wird ein zum Versetzen von Text verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-123">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="3ec1e-124">In diesem Beispiel erstellt eine geringfügig versetzte Kopie des Textes hinter dem primären Text einen Schatteneffekt.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-124">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
> <span data-ttu-id="3ec1e-125">Der <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> bietet eine Vielzahl von Funktionen für die Bereitstellung von Schatteneffekten.</span><span class="sxs-lookup"><span data-stu-id="3ec1e-125">The <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> provides a rich set of features for providing shadow effects.</span></span> <span data-ttu-id="3ec1e-126">Weitere Informationen finden Sie unter [Erstellen von Text mit einem Schatten](how-to-create-text-with-a-shadow.md).</span><span class="sxs-lookup"><span data-stu-id="3ec1e-126">For more information, see [Create Text with a Shadow](how-to-create-text-with-a-shadow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ec1e-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ec1e-127">See also</span></span>

- [<span data-ttu-id="3ec1e-128">Anwenden von Animationen auf Text</span><span class="sxs-lookup"><span data-stu-id="3ec1e-128">Apply Animations to Text</span></span>](how-to-apply-animations-to-text.md)
