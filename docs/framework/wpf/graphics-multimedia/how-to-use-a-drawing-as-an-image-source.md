---
title: 'Gewusst wie: Verwenden einer Zeichnung als Bildquelle'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5e0fe8f7d3633143348693c95d92dd2715bd0442
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a><span data-ttu-id="e3575-102">Gewusst wie: Verwenden einer Zeichnung als Bildquelle</span><span class="sxs-lookup"><span data-stu-id="e3575-102">How to: Use a Drawing as an Image Source</span></span>
<span data-ttu-id="e3575-103">Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.Drawing> als die <xref:System.Windows.Controls.Image.Source%2A> für ein <xref:System.Windows.Controls.Image> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="e3575-103">This example shows how to use a <xref:System.Windows.Media.Drawing> as the <xref:System.Windows.Controls.Image.Source%2A> for an <xref:System.Windows.Controls.Image> control.</span></span> <span data-ttu-id="e3575-104">Anzuzeigende eine <xref:System.Windows.Media.Drawing> mit eine <xref:System.Windows.Controls.Image> steuern, verwenden Sie eine <xref:System.Windows.Media.DrawingImage> als die <xref:System.Windows.Controls.Image> des Steuerelements <xref:System.Windows.Controls.Image.Source%2A> und legen Sie die <xref:System.Windows.Media.DrawingImage> des Objekts <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> Eigenschaft, um die Zeichnung angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3575-104">To display a <xref:System.Windows.Media.Drawing> with an <xref:System.Windows.Controls.Image> control, use a <xref:System.Windows.Media.DrawingImage> as the <xref:System.Windows.Controls.Image> control's <xref:System.Windows.Controls.Image.Source%2A> and set the <xref:System.Windows.Media.DrawingImage> object's <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> property to the drawing you want to display.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3575-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e3575-105">Example</span></span>  
 <span data-ttu-id="e3575-106">Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingImage> und ein <xref:System.Windows.Controls.Image> -Steuerelement zum Anzeigen einer <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="e3575-106">The following example uses a <xref:System.Windows.Media.DrawingImage> and an <xref:System.Windows.Controls.Image> control to display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="e3575-107">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e3575-107">This example produces the following output:</span></span>  
  
 <span data-ttu-id="e3575-108">![Eine GeometryDrawing von zwei Ellipsen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "Graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="e3575-108">![A GeometryDrawing of two ellipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
<span data-ttu-id="e3575-109">Ein DrawingImage</span><span class="sxs-lookup"><span data-stu-id="e3575-109">A DrawingImage</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e3575-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3575-110">See Also</span></span>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [<span data-ttu-id="e3575-111">Zeichnen eines Bilds mit ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="e3575-111">Draw an Image Using ImageDrawing</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)  
 [<span data-ttu-id="e3575-112">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="e3575-112">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="e3575-113">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="e3575-113">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="e3575-114">PresentationOptions:Freeze-Attribut</span><span class="sxs-lookup"><span data-stu-id="e3575-114">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
