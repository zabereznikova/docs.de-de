---
title: 'Vorgehensweise: Verwenden einer Zeichnung als Bildquelle'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
ms.openlocfilehash: 01c8cd65128ce4e78dcbf9e38519091767b7ba2f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499274"
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a><span data-ttu-id="0735e-102">Vorgehensweise: Verwenden einer Zeichnung als Bildquelle</span><span class="sxs-lookup"><span data-stu-id="0735e-102">How to: Use a Drawing as an Image Source</span></span>
<span data-ttu-id="0735e-103">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.Drawing> als die <xref:System.Windows.Controls.Image.Source%2A> für eine <xref:System.Windows.Controls.Image> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0735e-103">This example shows how to use a <xref:System.Windows.Media.Drawing> as the <xref:System.Windows.Controls.Image.Source%2A> for an <xref:System.Windows.Controls.Image> control.</span></span> <span data-ttu-id="0735e-104">Zum Anzeigen einer <xref:System.Windows.Media.Drawing> mit eine <xref:System.Windows.Controls.Image> steuern, verwenden Sie eine <xref:System.Windows.Media.DrawingImage> als die <xref:System.Windows.Controls.Image> des Steuerelements <xref:System.Windows.Controls.Image.Source%2A> und legen Sie die <xref:System.Windows.Media.DrawingImage> des Objekts <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> Eigenschaft, um die Zeichnung, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="0735e-104">To display a <xref:System.Windows.Media.Drawing> with an <xref:System.Windows.Controls.Image> control, use a <xref:System.Windows.Media.DrawingImage> as the <xref:System.Windows.Controls.Image> control's <xref:System.Windows.Controls.Image.Source%2A> and set the <xref:System.Windows.Media.DrawingImage> object's <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> property to the drawing you want to display.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0735e-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0735e-105">Example</span></span>  
 <span data-ttu-id="0735e-106">Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingImage> und <xref:System.Windows.Controls.Image> -Steuerelement zum Anzeigen einer <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="0735e-106">The following example uses a <xref:System.Windows.Media.DrawingImage> and an <xref:System.Windows.Controls.Image> control to display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="0735e-107">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="0735e-107">This example produces the following output:</span></span>  
  
 <span data-ttu-id="0735e-108">![Eine GeometryDrawing von zwei Ellipsen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "Graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="0735e-108">![A GeometryDrawing of two ellipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
<span data-ttu-id="0735e-109">Ein DrawingImage</span><span class="sxs-lookup"><span data-stu-id="0735e-109">A DrawingImage</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0735e-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0735e-110">See also</span></span>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="0735e-111">Zeichnen eines Bilds mit ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="0735e-111">Draw an Image Using ImageDrawing</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)
- [<span data-ttu-id="0735e-112">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="0735e-112">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="0735e-113">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="0735e-113">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [<span data-ttu-id="0735e-114">PresentationOptions:Freeze-Attribut</span><span class="sxs-lookup"><span data-stu-id="0735e-114">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
