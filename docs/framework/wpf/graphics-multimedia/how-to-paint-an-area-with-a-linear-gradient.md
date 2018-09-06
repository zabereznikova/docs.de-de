---
title: 'Gewusst wie: Zeichnen eines Bereichs mit einem linearen Farbverlauf'
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: aee9931fc366131ae492891cc4d0fff70b4a4441
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43779996"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="6fee2-102">Gewusst wie: Zeichnen eines Bereichs mit einem linearen Farbverlauf</span><span class="sxs-lookup"><span data-stu-id="6fee2-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="6fee2-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.LinearGradientBrush> -Klasse zum Zeichnen eines Bereichs mit einem linearen Farbverlauf.</span><span class="sxs-lookup"><span data-stu-id="6fee2-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="6fee2-104">Im folgenden Beispiel die <xref:System.Windows.Shapes.Shape.Fill%2A> von einem <xref:System.Windows.Shapes.Rectangle> einen diagonalen linearen Farbverlauf, der von Gelb zu Rot zu Blau Gelbgrün geht gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="6fee2-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fee2-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6fee2-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="6fee2-106">Die folgende Abbildung zeigt die im vorherigen Beispiel erstellten Farbverlauf.</span><span class="sxs-lookup"><span data-stu-id="6fee2-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="6fee2-107">![Diagonaler, linearer Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.jpg "Graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="6fee2-107">![Diagonal linear gradient](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="6fee2-108">Um einen horizontalen linearen Farbverlauf zu erstellen, Ändern der <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> von der <xref:System.Windows.Media.LinearGradientBrush> in (0,0.5) und (1,0.5 ändern).</span><span class="sxs-lookup"><span data-stu-id="6fee2-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="6fee2-109">Im folgenden Beispiel eine <xref:System.Windows.Shapes.Rectangle> einen horizontalen linearen Farbverlauf gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="6fee2-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="6fee2-110">Die folgende Abbildung zeigt die im vorherigen Beispiel erstellten Farbverlauf.</span><span class="sxs-lookup"><span data-stu-id="6fee2-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="6fee2-111">![Einen horizontalen linearen Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.jpg "Graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="6fee2-111">![A horizontal linear gradient](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="6fee2-112">Um ein vertikaler, linearer Farbverlauf zu erstellen, Ändern der <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> von der <xref:System.Windows.Media.LinearGradientBrush> in (0.5,0) und (0.5,1 ändern).</span><span class="sxs-lookup"><span data-stu-id="6fee2-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="6fee2-113">Im folgenden Beispiel eine <xref:System.Windows.Shapes.Rectangle> vertikaler, linearer Farbverlauf gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="6fee2-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="6fee2-114">Die folgende Abbildung zeigt die im vorherigen Beispiel erstellten Farbverlauf.</span><span class="sxs-lookup"><span data-stu-id="6fee2-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="6fee2-115">![Vertikaler, linearer Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.jpg "Graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="6fee2-115">![Vertical linear gradient](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fee2-116">In die Beispielen in diesem Thema verwenden das Standardkoordinatensystem zum Festlegen der Start- und Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="6fee2-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="6fee2-117">Das Standardkoordinatensystem ist relativ zu einem umgebenden Feld: 0 gibt 0 Prozent des umgebenden Felds, und 1 gibt 100 Prozent des umgebenden Felds.</span><span class="sxs-lookup"><span data-stu-id="6fee2-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="6fee2-118">Sie können dieses Koordinatensystem ändern, durch Festlegen der <xref:System.Windows.Media.GradientBrush.MappingMode%2A> -Eigenschaft auf den Wert <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6fee2-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6fee2-119">Ein absolutes Koordinatensystem ist nicht relativ zu einem umgebenden Feld.</span><span class="sxs-lookup"><span data-stu-id="6fee2-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="6fee2-120">Werte werden direkt im lokalen Raum interpretiert.</span><span class="sxs-lookup"><span data-stu-id="6fee2-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="6fee2-121">Weitere Beispiele finden Sie unter [Pinselbeispiel](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="6fee2-121">For additional examples, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="6fee2-122">Weitere Informationen über Farbverläufe und andere Typen von Pinseln, finden Sie unter [Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6fee2-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>
