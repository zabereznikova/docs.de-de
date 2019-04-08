---
title: 'Vorgehensweise: Erstellen einer Reflektion'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: 61b597cd36fcf0d60f215d9b5403f3b42b21dec4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105260"
---
# <a name="how-to-create-a-reflection"></a><span data-ttu-id="6b15a-102">Vorgehensweise: Erstellen einer Reflektion</span><span class="sxs-lookup"><span data-stu-id="6b15a-102">How to: Create a Reflection</span></span>
<span data-ttu-id="6b15a-103">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.VisualBrush> eine Reflektion erstellt.</span><span class="sxs-lookup"><span data-stu-id="6b15a-103">This example shows how to use a <xref:System.Windows.Media.VisualBrush> to create a reflection.</span></span> <span data-ttu-id="6b15a-104">Da eine <xref:System.Windows.Media.VisualBrush> können vorhandene visuelle anzeigen, Sie können diese Funktion verwenden, um interessante visuelle Effekte, z.B. Reflexionen und vergrößerungen zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="6b15a-104">Because a <xref:System.Windows.Media.VisualBrush> can display an existing visual, you can use this capability to produce interesting visual effects, such as reflections and magnification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b15a-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b15a-105">Example</span></span>  
 <span data-ttu-id="6b15a-106">Im folgenden Beispiel wird eine <xref:System.Windows.Media.VisualBrush> zum Erstellen einer Spiegelung einer <xref:System.Windows.Controls.Border> , das mehrere Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="6b15a-106">The following example uses a <xref:System.Windows.Media.VisualBrush> to create a reflection of a <xref:System.Windows.Controls.Border> that contains several elements.</span></span> <span data-ttu-id="6b15a-107">In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6b15a-107">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="6b15a-108">![Ein wiedergegeben visuellen Objekts](./media/graphicsmm-visualbrush-reflection-small.jpg "Graphicsmm_visualbrush_reflection_small")</span><span class="sxs-lookup"><span data-stu-id="6b15a-108">![A reflected Visual object](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span></span>  
<span data-ttu-id="6b15a-109">Ein reflektiertes Visual-Objekt</span><span class="sxs-lookup"><span data-stu-id="6b15a-109">A reflected Visual object</span></span>  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 <span data-ttu-id="6b15a-110">Das vollständige Beispiel, das Beispiele enthält, die zeigen, wie Sie Teile des Bildschirms zu vergrößern und Reflektionen erstellt werden, finden Sie unter [Beispiel zu VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049).</span><span class="sxs-lookup"><span data-stu-id="6b15a-110">For the complete sample, which includes examples that show how to magnify parts of the screen and how to create reflections, see [VisualBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160049).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b15a-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b15a-111">See also</span></span>

- <xref:System.Windows.Media.VisualBrush>
- [<span data-ttu-id="6b15a-112">Zeichnen mit Bildern, Zeichnungen und visuellen Elementen</span><span class="sxs-lookup"><span data-stu-id="6b15a-112">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
