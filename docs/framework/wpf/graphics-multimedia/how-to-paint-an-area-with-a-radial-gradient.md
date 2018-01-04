---
title: 'Gewusst wie: Zeichnen eines Bereichs mit einem radialen Farbverlauf'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f1da933a2ee7c179a55da7d33c61539d440eabc3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="6b46b-102">Gewusst wie: Zeichnen eines Bereichs mit einem radialen Farbverlauf</span><span class="sxs-lookup"><span data-stu-id="6b46b-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="6b46b-103">Dieses Beispiel zeigt, wie die <xref:System.Windows.Media.RadialGradientBrush> Klasse, um einen Bereich mit einem radialen Farbverlauf zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="6b46b-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b46b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b46b-104">Example</span></span>  
 <span data-ttu-id="6b46b-105">Im folgenden Beispiel wird eine <xref:System.Windows.Media.RadialGradientBrush> ein Rechteck mit einem radialen Farbverlauf gezeichnet, die von Gelb zu rot Gelbgrün Blau übergeht.</span><span class="sxs-lookup"><span data-stu-id="6b46b-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="6b46b-106">Die folgende Abbildung zeigt den Farbverlauf aus dem vorherigen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="6b46b-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="6b46b-107">Der Farbverlauf beendet wurden hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="6b46b-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="6b46b-108">![Farbverlaufstopps in einem radialen Farbverlauf](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "Wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="6b46b-108">![Gradient stops in a radial gradient](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b46b-109">In den Beispielen in diesem Thema verwenden Sie das Standard-Koordinatensystem für Steuerpunkte festlegen.</span><span class="sxs-lookup"><span data-stu-id="6b46b-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="6b46b-110">Der Standard-Koordinatensystem ist relativ zu einem umgebenden Feld: 0 gibt 0 Prozent des umgebenden Felds und 1 gibt 100 Prozent des umgebenden Felds an.</span><span class="sxs-lookup"><span data-stu-id="6b46b-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="6b46b-111">Sie können dieses Koordinatensystems ändern, durch Festlegen der <xref:System.Windows.Media.GradientBrush.MappingMode%2A> -Eigenschaft auf den Wert <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="6b46b-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="6b46b-112">Ein absolutes Koordinatensystem ist nicht relativ zu einem umgebenden Feld.</span><span class="sxs-lookup"><span data-stu-id="6b46b-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="6b46b-113">Werte werden direkt im lokalen Raum interpretiert.</span><span class="sxs-lookup"><span data-stu-id="6b46b-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="6b46b-114">Für zusätzliche <xref:System.Windows.Media.RadialGradientBrush> finden Sie unter der [Pinsel Beispiel](http://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="6b46b-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="6b46b-115">Weitere Informationen zu Farbverläufen und anderen Typen von Pinseln finden Sie unter [Zeichnen mit Volltonfarben und Farbverläufen (Übersicht)](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6b46b-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>
