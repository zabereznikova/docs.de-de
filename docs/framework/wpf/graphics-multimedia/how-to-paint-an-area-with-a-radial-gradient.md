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
ms.openlocfilehash: 75c28cd19ec0423589b6485884842468b89b5e8c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526790"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="e06c5-102">Gewusst wie: Zeichnen eines Bereichs mit einem radialen Farbverlauf</span><span class="sxs-lookup"><span data-stu-id="e06c5-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="e06c5-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.RadialGradientBrush> -Klasse zum Zeichnen eines Bereichs mit einem radialen Farbverlauf.</span><span class="sxs-lookup"><span data-stu-id="e06c5-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e06c5-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e06c5-104">Example</span></span>  
 <span data-ttu-id="e06c5-105">Im folgenden Beispiel wird eine <xref:System.Windows.Media.RadialGradientBrush> um ein Rechteck mit einem radialen Farbverlauf zu zeichnen, die von Gelb zu Rot zu Blau Gelbgrün geht.</span><span class="sxs-lookup"><span data-stu-id="e06c5-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="e06c5-106">Die folgende Abbildung zeigt den Farbverlauf aus dem vorherigen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="e06c5-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="e06c5-107">Die Farbverlaufsunterbrechungspunkte wurden hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="e06c5-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="e06c5-108">![Farbverlaufstopps in einem radialen Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "Wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="e06c5-108">![Gradient stops in a radial gradient](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e06c5-109">In die Beispielen in diesem Thema verwenden das Standardkoordinatensystem zum Festlegen der Control-Punkte.</span><span class="sxs-lookup"><span data-stu-id="e06c5-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="e06c5-110">Das Standardkoordinatensystem ist relativ zu einem umgebenden Feld: 0 gibt 0 Prozent des umgebenden Felds, und 1 gibt 100 Prozent des umgebenden Felds.</span><span class="sxs-lookup"><span data-stu-id="e06c5-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="e06c5-111">Sie können dieses Koordinatensystem ändern, durch Festlegen der <xref:System.Windows.Media.GradientBrush.MappingMode%2A> -Eigenschaft auf den Wert <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="e06c5-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="e06c5-112">Ein absolutes Koordinatensystem ist nicht relativ zu einem umgebenden Feld.</span><span class="sxs-lookup"><span data-stu-id="e06c5-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="e06c5-113">Werte werden direkt im lokalen Raum interpretiert.</span><span class="sxs-lookup"><span data-stu-id="e06c5-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="e06c5-114">Für zusätzliche <xref:System.Windows.Media.RadialGradientBrush> finden Sie unter den [Pinselbeispiel](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="e06c5-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="e06c5-115">Weitere Informationen über Farbverläufe und andere Typen von Pinseln, finden Sie unter [Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e06c5-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>
