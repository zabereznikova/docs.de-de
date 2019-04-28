---
title: 'Vorgehensweise: Verwenden einer Zeichnung als Bildquelle'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
ms.openlocfilehash: d4b91a6495e1c54400d5fbfe43b6311d908565a7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769356"
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a><span data-ttu-id="65a5f-102">Vorgehensweise: Verwenden einer Zeichnung als Bildquelle</span><span class="sxs-lookup"><span data-stu-id="65a5f-102">How to: Use a Drawing as an Image Source</span></span>
<span data-ttu-id="65a5f-103">Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.Drawing> als die <xref:System.Windows.Controls.Image.Source%2A> für eine <xref:System.Windows.Controls.Image> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="65a5f-103">This example shows how to use a <xref:System.Windows.Media.Drawing> as the <xref:System.Windows.Controls.Image.Source%2A> for an <xref:System.Windows.Controls.Image> control.</span></span> <span data-ttu-id="65a5f-104">Zum Anzeigen einer <xref:System.Windows.Media.Drawing> mit eine <xref:System.Windows.Controls.Image> steuern, verwenden Sie eine <xref:System.Windows.Media.DrawingImage> als die <xref:System.Windows.Controls.Image> des Steuerelements <xref:System.Windows.Controls.Image.Source%2A> und legen Sie die <xref:System.Windows.Media.DrawingImage> des Objekts <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> Eigenschaft, um die Zeichnung, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="65a5f-104">To display a <xref:System.Windows.Media.Drawing> with an <xref:System.Windows.Controls.Image> control, use a <xref:System.Windows.Media.DrawingImage> as the <xref:System.Windows.Controls.Image> control's <xref:System.Windows.Controls.Image.Source%2A> and set the <xref:System.Windows.Media.DrawingImage> object's <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> property to the drawing you want to display.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65a5f-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="65a5f-105">Example</span></span>  
 <span data-ttu-id="65a5f-106">Im folgenden Beispiel wird eine <xref:System.Windows.Media.DrawingImage> und <xref:System.Windows.Controls.Image> -Steuerelement zum Anzeigen einer <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="65a5f-106">The following example uses a <xref:System.Windows.Media.DrawingImage> and an <xref:System.Windows.Controls.Image> control to display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="65a5f-107">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="65a5f-107">This example produces the following output:</span></span>  
  
 <span data-ttu-id="65a5f-108">![Eine GeometryDrawing von zwei Ellipsen](./media/graphicsmm-geodraw.jpg "Graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="65a5f-108">![A GeometryDrawing of two ellipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
<span data-ttu-id="65a5f-109">Ein DrawingImage</span><span class="sxs-lookup"><span data-stu-id="65a5f-109">A DrawingImage</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="65a5f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65a5f-110">See also</span></span>

- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="65a5f-111">Zeichnen eines Bilds mit ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="65a5f-111">Draw an Image Using ImageDrawing</span></span>](how-to-draw-an-image-using-imagedrawing.md)
- [<span data-ttu-id="65a5f-112">Übersicht über Zeichnungsobjekte</span><span class="sxs-lookup"><span data-stu-id="65a5f-112">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="65a5f-113">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="65a5f-113">Freezable Objects Overview</span></span>](../advanced/freezable-objects-overview.md)
- [<span data-ttu-id="65a5f-114">PresentationOptions:Freeze-Attribut</span><span class="sxs-lookup"><span data-stu-id="65a5f-114">PresentationOptions:Freeze Attribute</span></span>](../advanced/presentationoptions-freeze-attribute.md)
