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
ms.openlocfilehash: 8a5ed345c0aa25312bd74799264e1f66ab4554e0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452057"
---
# <a name="how-to-create-a-reflection"></a><span data-ttu-id="ef589-102">Gewusst wie: Erstellen einer Reflektion</span><span class="sxs-lookup"><span data-stu-id="ef589-102">How to: Create a Reflection</span></span>
<span data-ttu-id="ef589-103">In diesem Beispiel wird gezeigt, wie ein <xref:System.Windows.Media.VisualBrush> zum Erstellen einer Reflektion verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ef589-103">This example shows how to use a <xref:System.Windows.Media.VisualBrush> to create a reflection.</span></span> <span data-ttu-id="ef589-104">Da eine <xref:System.Windows.Media.VisualBrush> ein vorhandenes visuelles Element anzeigen kann, können Sie diese Funktion verwenden, um interessante visuelle Effekte, wie z. b. Reflektionen und Vergrößerung, zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="ef589-104">Because a <xref:System.Windows.Media.VisualBrush> can display an existing visual, you can use this capability to produce interesting visual effects, such as reflections and magnification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef589-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef589-105">Example</span></span>  
 <span data-ttu-id="ef589-106">Im folgenden Beispiel wird ein-<xref:System.Windows.Media.VisualBrush> verwendet, um eine Reflektion einer <xref:System.Windows.Controls.Border> zu erstellen, die mehrere-Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="ef589-106">The following example uses a <xref:System.Windows.Media.VisualBrush> to create a reflection of a <xref:System.Windows.Controls.Border> that contains several elements.</span></span> <span data-ttu-id="ef589-107">In der folgenden Abbildung ist die von diesem Beispiel erstellte Ausgabe dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ef589-107">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="ef589-108">![Ein reflektiertes Visual-Objekt](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span><span class="sxs-lookup"><span data-stu-id="ef589-108">![A reflected Visual object](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span></span>  
<span data-ttu-id="ef589-109">Ein reflektiertes Visual-Objekt</span><span class="sxs-lookup"><span data-stu-id="ef589-109">A reflected Visual object</span></span>  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 <span data-ttu-id="ef589-110">Das vollständige Beispiel, das Beispiele enthält, die veranschaulichen, wie Teile des Bildschirms vergrößert werden und wie Sie Reflektionen erstellen, finden Sie unter [VisualBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush).</span><span class="sxs-lookup"><span data-stu-id="ef589-110">For the complete sample, which includes examples that show how to magnify parts of the screen and how to create reflections, see [VisualBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef589-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef589-111">See also</span></span>

- <xref:System.Windows.Media.VisualBrush>
- [<span data-ttu-id="ef589-112">Zeichnen mit Bildern, Zeichnungen und visuellen Elementen</span><span class="sxs-lookup"><span data-stu-id="ef589-112">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
