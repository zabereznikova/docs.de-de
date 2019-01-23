---
title: 'Vorgehensweise: Auflisten des Zeichnungsinhalts eines visuellen Objekts'
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: a3131b6c86b0f6a7aa79cca305b9c3b2496346f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561947"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a><span data-ttu-id="612e5-102">Vorgehensweise: Auflisten des Zeichnungsinhalts eines visuellen Objekts</span><span class="sxs-lookup"><span data-stu-id="612e5-102">How to: Enumerate Drawing Content of a Visual</span></span>
<span data-ttu-id="612e5-103">Die <xref:System.Windows.Media.Drawing> Objekt stellt ein Objektmodell bereit, für das Auflisten des Inhalts einer <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="612e5-103">The <xref:System.Windows.Media.Drawing> object provide an object model for enumerating the contents of a <xref:System.Windows.Media.Visual>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="612e5-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="612e5-104">Example</span></span>  
 <span data-ttu-id="612e5-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> Methode zum Abrufen der <xref:System.Windows.Media.DrawingGroup> Wert eine <xref:System.Windows.Media.Visual> zählt Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="612e5-105">The following example uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method to retrieve the <xref:System.Windows.Media.DrawingGroup> value of a <xref:System.Windows.Media.Visual> and enumerate it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="612e5-106">Wenn Sie den Inhalt des visuellen Objekts auflisten, rufen Sie <xref:System.Windows.Media.Drawing> Objekte und nicht die zugrunde liegende Darstellung der Renderingdaten als Anweisungsliste für Vektorgrafiken.</span><span class="sxs-lookup"><span data-stu-id="612e5-106">When you are enumerating the contents of the visual, you are retrieving <xref:System.Windows.Media.Drawing> objects, and not the underlying representation of the render data as a vector graphics instruction list.</span></span> <span data-ttu-id="612e5-107">Weitere Informationen finden Sie unter [Übersicht über das WPF-Grafikenrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="612e5-107">For more information, see [WPF Graphics Rendering Overview](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a><span data-ttu-id="612e5-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="612e5-108">See also</span></span>
- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [<span data-ttu-id="612e5-109">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="612e5-109">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="612e5-110">Übersicht über das WPF-Grafikrendering</span><span class="sxs-lookup"><span data-stu-id="612e5-110">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
