---
title: 'Gewusst wie: Erstellen einer Reflektion'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: 716adff5c5c41e6601e384b6669516cb6ba1041d
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46477622"
---
# <a name="how-to-create-a-reflection"></a><span data-ttu-id="70c2c-102">Gewusst wie: Erstellen einer Reflektion</span><span class="sxs-lookup"><span data-stu-id="70c2c-102">How to: Create a Reflection</span></span>
<span data-ttu-id="70c2c-103">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.VisualBrush> eine Reflektion erstellt.</span><span class="sxs-lookup"><span data-stu-id="70c2c-103">This example shows how to use a <xref:System.Windows.Media.VisualBrush> to create a reflection.</span></span> <span data-ttu-id="70c2c-104">Da eine <xref:System.Windows.Media.VisualBrush> können vorhandene visuelle anzeigen, Sie können diese Funktion verwenden, um interessante visuelle Effekte, z.B. Reflexionen und vergrößerungen zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="70c2c-104">Because a <xref:System.Windows.Media.VisualBrush> can display an existing visual, you can use this capability to produce interesting visual effects, such as reflections and magnification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70c2c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70c2c-105">Example</span></span>  
 <span data-ttu-id="70c2c-106">Im folgenden Beispiel wird eine <xref:System.Windows.Media.VisualBrush> zum Erstellen einer Spiegelung einer <xref:System.Windows.Controls.Border> , das mehrere Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="70c2c-106">The following example uses a <xref:System.Windows.Media.VisualBrush> to create a reflection of a <xref:System.Windows.Controls.Border> that contains several elements.</span></span> <span data-ttu-id="70c2c-107">In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.</span><span class="sxs-lookup"><span data-stu-id="70c2c-107">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="70c2c-108">![Ein wiedergegeben visuellen Objekts](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "Graphicsmm_visualbrush_reflection_small")</span><span class="sxs-lookup"><span data-stu-id="70c2c-108">![A reflected Visual object](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span></span>  
<span data-ttu-id="70c2c-109">Ein reflektiertes Visual-Objekt</span><span class="sxs-lookup"><span data-stu-id="70c2c-109">A reflected Visual object</span></span>  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 <span data-ttu-id="70c2c-110">Das vollständige Beispiel, das Beispiele enthält, die zeigen, wie Sie Teile des Bildschirms zu vergrößern und Reflektionen erstellt werden, finden Sie unter [Beispiel zu VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049).</span><span class="sxs-lookup"><span data-stu-id="70c2c-110">For the complete sample, which includes examples that show how to magnify parts of the screen and how to create reflections, see [VisualBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160049).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70c2c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70c2c-111">See Also</span></span>  
 <xref:System.Windows.Media.VisualBrush>  
 [<span data-ttu-id="70c2c-112">Zeichnen mit Bildern, Zeichnungen und visuellen Elementen</span><span class="sxs-lookup"><span data-stu-id="70c2c-112">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
