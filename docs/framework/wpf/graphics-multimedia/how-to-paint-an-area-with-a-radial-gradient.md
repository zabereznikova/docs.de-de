---
title: 'Gewusst wie: Zeichnen eines Bereichs mit einem radialen Farbverlauf'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: 8a53d5d7247f82905816265f7c92b22f287591c5
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452752"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="703fc-102">Gewusst wie: Zeichnen eines Bereichs mit einem radialen Farbverlauf</span><span class="sxs-lookup"><span data-stu-id="703fc-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="703fc-103">Dieses Beispiel zeigt, wie Sie die <xref:System.Windows.Media.RadialGradientBrush>-Klasse verwenden, um einen Bereich mit einem radialen Farbverlauf zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="703fc-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="703fc-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="703fc-104">Example</span></span>  
 <span data-ttu-id="703fc-105">Im folgenden Beispiel wird ein Rechteck mit einem <xref:System.Windows.Media.RadialGradientBrush> verwendet, um ein Rechteck mit einem radialen Farbverlauf zu zeichnen, der von gelb zu rot zu blau in Kalk grün übergeht.</span><span class="sxs-lookup"><span data-stu-id="703fc-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="703fc-106">Die folgende Abbildung zeigt den Farbverlauf aus dem vorherigen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="703fc-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="703fc-107">Die Verlaufs Stopps wurden hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="703fc-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="703fc-108">![Farbverlaufs Stopps in einem radialen Farbverlauf](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="703fc-108">![Gradient stops in a radial gradient](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="703fc-109">In den Beispielen in diesem Thema wird das Standard Koordinatensystem zum Festlegen von Steuerungs Punkten verwendet.</span><span class="sxs-lookup"><span data-stu-id="703fc-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="703fc-110">Das Standard Koordinatensystem ist relativ zu einem umgebenden Feld: 0 gibt 0 Prozent des umgebenden Felds an, und 1 gibt 100 Prozent des umgebenden Felds an.</span><span class="sxs-lookup"><span data-stu-id="703fc-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="703fc-111">Sie können dieses Koordinatensystem ändern, indem Sie die <xref:System.Windows.Media.GradientBrush.MappingMode%2A>-Eigenschaft auf den Wert <xref:System.Windows.Media.BrushMappingMode.Absolute>festlegen.</span><span class="sxs-lookup"><span data-stu-id="703fc-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="703fc-112">Ein absolutes Koordinatensystem ist nicht relativ zu einem umgebenden Feld.</span><span class="sxs-lookup"><span data-stu-id="703fc-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="703fc-113">Werte werden direkt im lokalen Raum interpretiert.</span><span class="sxs-lookup"><span data-stu-id="703fc-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="703fc-114">Weitere <xref:System.Windows.Media.RadialGradientBrush> Beispiele finden Sie im [Beispiel Pinsel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="703fc-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="703fc-115">Weitere Informationen zu Farbverläufen und anderen Pinseltypen finden Sie unter Übersicht über das Zeichnen [mit voll Tonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="703fc-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
