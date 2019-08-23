---
title: 'Vorgehensweise: Auflisten des Zeichnungsinhalts eines visuellen Objekts'
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 25aa0c3706005c1e16cedd7e06914db764545ebb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930071"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a><span data-ttu-id="2ddcb-102">Vorgehensweise: Auflisten des Zeichnungsinhalts eines visuellen Objekts</span><span class="sxs-lookup"><span data-stu-id="2ddcb-102">How to: Enumerate Drawing Content of a Visual</span></span>
<span data-ttu-id="2ddcb-103">Das <xref:System.Windows.Media.Drawing> -Objekt stellt ein Objektmodell für das Auflisten des Inhalts <xref:System.Windows.Media.Visual>eines bereit.</span><span class="sxs-lookup"><span data-stu-id="2ddcb-103">The <xref:System.Windows.Media.Drawing> object provide an object model for enumerating the contents of a <xref:System.Windows.Media.Visual>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ddcb-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ddcb-104">Example</span></span>  
 <span data-ttu-id="2ddcb-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> <xref:System.Windows.Media.Visual> -Methode verwendet, <xref:System.Windows.Media.DrawingGroup> um den Wert eines abzurufen und ihn aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="2ddcb-105">The following example uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method to retrieve the <xref:System.Windows.Media.DrawingGroup> value of a <xref:System.Windows.Media.Visual> and enumerate it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ddcb-106">Wenn Sie den Inhalt der Visualisierung auflisten, rufen Sie <xref:System.Windows.Media.Drawing> Objekte ab, und nicht die zugrunde liegende Darstellung der Renderingdaten als Liste von Vektorgrafik Anweisungs Listen.</span><span class="sxs-lookup"><span data-stu-id="2ddcb-106">When you are enumerating the contents of the visual, you are retrieving <xref:System.Windows.Media.Drawing> objects, and not the underlying representation of the render data as a vector graphics instruction list.</span></span> <span data-ttu-id="2ddcb-107">Weitere Informationen finden Sie unter [Übersicht über das WPF-Grafikenrendering](wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2ddcb-107">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a><span data-ttu-id="2ddcb-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ddcb-108">See also</span></span>

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [<span data-ttu-id="2ddcb-109">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="2ddcb-109">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="2ddcb-110">Übersicht über das WPF-Grafikrendering</span><span class="sxs-lookup"><span data-stu-id="2ddcb-110">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
