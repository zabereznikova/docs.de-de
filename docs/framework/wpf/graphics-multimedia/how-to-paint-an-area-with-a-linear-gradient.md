---
title: 'Vorgehensweise: Zeichnen eines Bereichs mit einem linearen Farbverlauf'
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: c48ff13811d784ecc7042b73b964a9e6f2d42a34
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367244"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="e8840-102">Vorgehensweise: Zeichnen eines Bereichs mit einem linearen Farbverlauf</span><span class="sxs-lookup"><span data-stu-id="e8840-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="e8840-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.LinearGradientBrush> -Klasse zum Zeichnen eines Bereichs mit einem linearen Farbverlauf.</span><span class="sxs-lookup"><span data-stu-id="e8840-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="e8840-104">Im folgenden Beispiel die <xref:System.Windows.Shapes.Shape.Fill%2A> von einem <xref:System.Windows.Shapes.Rectangle> einen diagonalen linearen Farbverlauf, der von Gelb zu Rot zu Blau Gelbgrün geht gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="e8840-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8840-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e8840-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="e8840-106">Die folgende Abbildung zeigt die im vorherigen Beispiel erstellten Farbverlauf.</span><span class="sxs-lookup"><span data-stu-id="e8840-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="e8840-107">![Diagonaler, linearer Farbverlauf](./media/graphicsmm-diagonallgb.jpg "Graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="e8840-107">![Diagonal linear gradient](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="e8840-108">Um einen horizontalen linearen Farbverlauf zu erstellen, Ändern der <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> von der <xref:System.Windows.Media.LinearGradientBrush> in (0,0.5) und (1,0.5 ändern).</span><span class="sxs-lookup"><span data-stu-id="e8840-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="e8840-109">Im folgenden Beispiel eine <xref:System.Windows.Shapes.Rectangle> einen horizontalen linearen Farbverlauf gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="e8840-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="e8840-110">Die folgende Abbildung zeigt die im vorherigen Beispiel erstellten Farbverlauf.</span><span class="sxs-lookup"><span data-stu-id="e8840-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="e8840-111">![Einen horizontalen linearen Farbverlauf](./media/graphicsmm-horizontallgb.jpg "Graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="e8840-111">![A horizontal linear gradient](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="e8840-112">Um ein vertikaler, linearer Farbverlauf zu erstellen, Ändern der <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> und <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> von der <xref:System.Windows.Media.LinearGradientBrush> in (0.5,0) und (0.5,1 ändern).</span><span class="sxs-lookup"><span data-stu-id="e8840-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="e8840-113">Im folgenden Beispiel eine <xref:System.Windows.Shapes.Rectangle> vertikaler, linearer Farbverlauf gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="e8840-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="e8840-114">Die folgende Abbildung zeigt die im vorherigen Beispiel erstellten Farbverlauf.</span><span class="sxs-lookup"><span data-stu-id="e8840-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="e8840-115">![Vertikaler, linearer Farbverlauf](./media/graphicsmm-verticallgb.jpg "Graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="e8840-115">![Vertical linear gradient](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8840-116">In die Beispielen in diesem Thema verwenden das Standardkoordinatensystem zum Festlegen der Start- und Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="e8840-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="e8840-117">Das Standardkoordinatensystem ist relativ zu einem umgebenden Feld: 0 gibt 0 Prozent des umgebenden Felds, und 1 gibt 100 Prozent des umgebenden Felds.</span><span class="sxs-lookup"><span data-stu-id="e8840-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="e8840-118">Sie können dieses Koordinatensystem ändern, durch Festlegen der <xref:System.Windows.Media.GradientBrush.MappingMode%2A> -Eigenschaft auf den Wert <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e8840-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e8840-119">Ein absolutes Koordinatensystem ist nicht relativ zu einem umgebenden Feld.</span><span class="sxs-lookup"><span data-stu-id="e8840-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="e8840-120">Werte werden direkt im lokalen Raum interpretiert.</span><span class="sxs-lookup"><span data-stu-id="e8840-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="e8840-121">Weitere Beispiele finden Sie unter [Pinselbeispiel](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="e8840-121">For additional examples, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="e8840-122">Weitere Informationen über Farbverläufe und andere Typen von Pinseln, finden Sie unter [Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e8840-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
