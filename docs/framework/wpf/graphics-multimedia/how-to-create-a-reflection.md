---
title: 'Gewusst wie: Erstellen einer Reflektion'
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
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 157bc01e23c304531f04b0a1cc7a66bad4bb3934
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-reflection"></a><span data-ttu-id="36893-102">Gewusst wie: Erstellen einer Reflektion</span><span class="sxs-lookup"><span data-stu-id="36893-102">How to: Create a Reflection</span></span>
<span data-ttu-id="36893-103">Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.VisualBrush> eine Reflektion erstellt.</span><span class="sxs-lookup"><span data-stu-id="36893-103">This example shows how to use a <xref:System.Windows.Media.VisualBrush> to create a reflection.</span></span> <span data-ttu-id="36893-104">Da eine <xref:System.Windows.Media.VisualBrush> vorhandene visuelle angezeigt werden können, können Sie diese Funktion verwenden, um interessante visuelle Effekte wie Reflektionen und Vergrößerung zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="36893-104">Because a <xref:System.Windows.Media.VisualBrush> can display an existing visual, you can use this capability to produce interesting visual effects, such as reflections and magnification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36893-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="36893-105">Example</span></span>  
 <span data-ttu-id="36893-106">Im folgenden Beispiel wird eine <xref:System.Windows.Media.VisualBrush> zum Erstellen einer Spiegelung einer <xref:System.Windows.Controls.Border> , die mehrere Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="36893-106">The following example uses a <xref:System.Windows.Media.VisualBrush> to create a reflection of a <xref:System.Windows.Controls.Border> that contains several elements.</span></span> <span data-ttu-id="36893-107">In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.</span><span class="sxs-lookup"><span data-stu-id="36893-107">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="36893-108">![Ein reflektiert visuelles Objekt](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "Graphicsmm_visualbrush_reflection_small")</span><span class="sxs-lookup"><span data-stu-id="36893-108">![A reflected Visual object](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span></span>  
<span data-ttu-id="36893-109">Ein reflektiertes Visual-Objekt</span><span class="sxs-lookup"><span data-stu-id="36893-109">A reflected Visual object</span></span>  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 <span data-ttu-id="36893-110">Das vollständige Beispiel, das Beispiele, die zum Teilen des Bildschirms vergrößern und zur Erstellung von Reflektionen anzeigen enthält, finden Sie unter [VisualBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160049).</span><span class="sxs-lookup"><span data-stu-id="36893-110">For the complete sample, which includes examples that show how to magnify parts of the screen and how to create reflections, see [VisualBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160049).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36893-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36893-111">See Also</span></span>  
 <xref:System.Windows.Media.VisualBrush>  
 [<span data-ttu-id="36893-112">Zeichnen mit Bildern, Zeichnungen und visuellen Elementen</span><span class="sxs-lookup"><span data-stu-id="36893-112">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
