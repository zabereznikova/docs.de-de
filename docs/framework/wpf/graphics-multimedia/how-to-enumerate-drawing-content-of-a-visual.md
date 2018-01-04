---
title: 'Gewusst wie: Auflisten des Zeichnungsinhalts eines visuellen Objekts'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5c97926286076149a6eedf34bb70bbc76b2e0d8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a><span data-ttu-id="78fc0-102">Gewusst wie: Auflisten des Zeichnungsinhalts eines visuellen Objekts</span><span class="sxs-lookup"><span data-stu-id="78fc0-102">How to: Enumerate Drawing Content of a Visual</span></span>
<span data-ttu-id="78fc0-103">Die <xref:System.Windows.Media.Drawing> Objekt enthalten ein Objektmodell zum Aufzählen der Inhalt von einem <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="78fc0-103">The <xref:System.Windows.Media.Drawing> object provide an object model for enumerating the contents of a <xref:System.Windows.Media.Visual>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78fc0-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="78fc0-104">Example</span></span>  
 <span data-ttu-id="78fc0-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> Methode zum Abrufen der <xref:System.Windows.Media.DrawingGroup> Wert, der eine <xref:System.Windows.Media.Visual> und aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="78fc0-105">The following example uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method to retrieve the <xref:System.Windows.Media.DrawingGroup> value of a <xref:System.Windows.Media.Visual> and enumerate it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78fc0-106">Wenn Sie den Inhalt des visuellen Elements auflisten, rufen Sie <xref:System.Windows.Media.Drawing> Objekte und nicht die zugrunde liegende Darstellung der Renderingdaten als Anweisungsliste für Vektor.</span><span class="sxs-lookup"><span data-stu-id="78fc0-106">When you are enumerating the contents of the visual, you are retrieving <xref:System.Windows.Media.Drawing> objects, and not the underlying representation of the render data as a vector graphics instruction list.</span></span> <span data-ttu-id="78fc0-107">Weitere Informationen finden Sie unter [Übersicht über das WPF-Grafikenrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="78fc0-107">For more information, see [WPF Graphics Rendering Overview](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a><span data-ttu-id="78fc0-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78fc0-108">See Also</span></span>  
 <xref:System.Windows.Media.Drawing>  
 <xref:System.Windows.Media.DrawingGroup>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 [<span data-ttu-id="78fc0-109">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="78fc0-109">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="78fc0-110">Übersicht über das WPF-Grafikrendering</span><span class="sxs-lookup"><span data-stu-id="78fc0-110">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
