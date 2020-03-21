---
title: 'Gewusst wie: Skalieren eines Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 34d954f68747be9eedc0ef71634e0c18b411d260
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112049"
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="cac2e-102">Gewusst wie: Skalieren eines Elements</span><span class="sxs-lookup"><span data-stu-id="cac2e-102">How to: Scale an Element</span></span>
<span data-ttu-id="cac2e-103">In diesem Beispiel wird <xref:System.Windows.Media.ScaleTransform> gezeigt, wie ein Element skaliert wird.</span><span class="sxs-lookup"><span data-stu-id="cac2e-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="cac2e-104">Verwenden <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Sie <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> die und Eigenschaften, um die Größe des Elements um den angegebenen Faktor zu ändern.</span><span class="sxs-lookup"><span data-stu-id="cac2e-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="cac2e-105">Ein <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Wert von 1,5 dehnt das Element beispielsweise auf 150 Prozent seiner ursprünglichen Breite aus.</span><span class="sxs-lookup"><span data-stu-id="cac2e-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="cac2e-106">Bei <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> einem Wert von 0,5 wird die Höhe eines Elements um 50 Prozent verkleinert.</span><span class="sxs-lookup"><span data-stu-id="cac2e-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="cac2e-107">Verwenden <xref:System.Windows.Media.ScaleTransform.CenterX%2A> Sie <xref:System.Windows.Media.ScaleTransform.CenterY%2A> die und Eigenschaften, um den Punkt anzugeben, der den Mittelpunkt des Skalierungsvorgangs ist.</span><span class="sxs-lookup"><span data-stu-id="cac2e-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="cac2e-108">Standardmäßig wird <xref:System.Windows.Media.ScaleTransform> a am Punkt (0,0) zentriert, der der oberen linken Ecke des Rechtecks entspricht.</span><span class="sxs-lookup"><span data-stu-id="cac2e-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="cac2e-109">Dies hat den Effekt, dass das Element bewegt und auch <xref:System.Windows.Media.Transform>größer angezeigt wird, da Sie beim Anwenden eines den Koordinatenraum ändern, in dem sich das Objekt befindet.</span><span class="sxs-lookup"><span data-stu-id="cac2e-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="cac2e-110">Im folgenden Beispiel <xref:System.Windows.Media.ScaleTransform> wird eine verwendet, um die Größe <xref:System.Windows.Shapes.Rectangle>eines 50-mal-50 zu verdoppeln.</span><span class="sxs-lookup"><span data-stu-id="cac2e-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="cac2e-111">Der <xref:System.Windows.Media.ScaleTransform> hat den Wert 0 (Standardwert) für beide <xref:System.Windows.Media.ScaleTransform.CenterX%2A> und <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span><span class="sxs-lookup"><span data-stu-id="cac2e-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cac2e-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cac2e-112">Example</span></span>  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="cac2e-113">In der <xref:System.Windows.Media.ScaleTransform.CenterX%2A> Regel <xref:System.Windows.Media.ScaleTransform.CenterY%2A> legen Sie und auf die Mitte<xref:System.Windows.FrameworkElement.Width%2A>des <xref:System.Windows.FrameworkElement.Height%2A>Objekts, das skaliert wird: ( /2, /2).</span><span class="sxs-lookup"><span data-stu-id="cac2e-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="cac2e-114">Das folgende Beispiel <xref:System.Windows.Shapes.Rectangle> zeigt ein anderes, das doppelt so groß ist. Dies <xref:System.Windows.Media.ScaleTransform> hat jedoch einen Wert <xref:System.Windows.Media.ScaleTransform.CenterX%2A> von <xref:System.Windows.Media.ScaleTransform.CenterY%2A>25 für beide und , was der Mitte des Rechtecks entspricht.</span><span class="sxs-lookup"><span data-stu-id="cac2e-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="cac2e-115">Die folgende Abbildung zeigt den <xref:System.Windows.Media.ScaleTransform> Unterschied zwischen den beiden Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="cac2e-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="cac2e-116">Die gepunktete Linie stellt die Größe und die Position des Rechtecks vor der Skalierung dar.</span><span class="sxs-lookup"><span data-stu-id="cac2e-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="cac2e-117">![2-fach-Skalierung mit unterschiedlichen Mittelpunkten](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="cac2e-117">![2x scales with different center points](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="cac2e-118">Zwei ScaleTransform-Vorgänge mit identischen ScaleX- und ScaleY-Werten aber unterschiedlichen Mittelpunkten</span><span class="sxs-lookup"><span data-stu-id="cac2e-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="cac2e-119">Das vollständige Beispiel finden Sie unter [2D-Transformationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="cac2e-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cac2e-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cac2e-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="cac2e-121">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="cac2e-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="cac2e-122">How-to-Themen</span><span class="sxs-lookup"><span data-stu-id="cac2e-122">How-to Topics</span></span>](transformations-how-to-topics.md)
