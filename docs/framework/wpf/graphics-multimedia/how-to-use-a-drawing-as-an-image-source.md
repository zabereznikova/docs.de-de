---
title: 'Gewusst wie: Verwenden einer Zeichnung als Bildquelle'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
ms.openlocfilehash: 7da8a2a594b0562667aaf417d736159d98818a63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562285"
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a><span data-ttu-id="a8981-102">Gewusst wie: Verwenden einer Zeichnung als Bildquelle</span><span class="sxs-lookup"><span data-stu-id="a8981-102">How to: Use a Drawing as an Image Source</span></span>
<span data-ttu-id="a8981-103">Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.Drawing> als die <xref:System.Windows.Controls.Image.Source%2A> für ein <xref:System.Windows.Controls.Image> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="a8981-103">This example shows how to use a <xref:System.Windows.Media.Drawing> as the <xref:System.Windows.Controls.Image.Source%2A> for an <xref:System.Windows.Controls.Image> control.</span></span> <span data-ttu-id="a8981-104">Anzuzeigende eine <xref:System.Windows.Media.Drawing> mit eine <xref:System.Windows.Controls.Image> steuern, verwenden Sie eine <xref:System.Windows.Media.DrawingImage> als die <xref:System.Windows.Controls.Image> des Steuerelements <xref:System.Windows.Controls.Image.Source%2A> und legen Sie die <xref:System.Windows.Media.DrawingImage> des Objekts <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> Eigenschaft, um die Zeichnung angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a8981-104">To display a <xref:System.Windows.Media.Drawing> with an <xref:System.Windows.Controls.Image> control, use a <xref:System.Windows.Media.DrawingImage> as the <xref:System.Windows.Controls.Image> control's <xref:System.Windows.Controls.Image.Source%2A> and set the <xref:System.Windows.Media.DrawingImage> object's <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> property to the drawing you want to display.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8981-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a8981-105">Example</span></span>  
 <span data-ttu-id="a8981-106">Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingImage> und ein <xref:System.Windows.Controls.Image> -Steuerelement zum Anzeigen einer <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="a8981-106">The following example uses a <xref:System.Windows.Media.DrawingImage> and an <xref:System.Windows.Controls.Image> control to display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="a8981-107">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a8981-107">This example produces the following output:</span></span>  
  
 <span data-ttu-id="a8981-108">![Eine GeometryDrawing von zwei Ellipsen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "Graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="a8981-108">![A GeometryDrawing of two ellipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
<span data-ttu-id="a8981-109">Ein DrawingImage</span><span class="sxs-lookup"><span data-stu-id="a8981-109">A DrawingImage</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a8981-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8981-110">See Also</span></span>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [<span data-ttu-id="a8981-111">Zeichnen eines Bilds mit ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="a8981-111">Draw an Image Using ImageDrawing</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)  
 [<span data-ttu-id="a8981-112">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="a8981-112">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="a8981-113">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="a8981-113">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="a8981-114">PresentationOptions:Freeze-Attribut</span><span class="sxs-lookup"><span data-stu-id="a8981-114">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
