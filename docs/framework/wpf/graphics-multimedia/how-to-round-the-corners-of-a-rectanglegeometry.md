---
title: 'Vorgehensweise: Abrunden der Ecken einer RectangleGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
ms.openlocfilehash: eb2f173bedb903e12b2795264c684524cfa09825
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089132"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a><span data-ttu-id="a2716-102">Vorgehensweise: Abrunden der Ecken einer RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="a2716-102">How to: Round the Corners of a RectangleGeometry</span></span>
<span data-ttu-id="a2716-103">Zum Abrunden der Ecken des eine <xref:System.Windows.Media.RectangleGeometry>legen die <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> und <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> Eigenschaften, die einen Wert größer als 0 (null).</span><span class="sxs-lookup"><span data-stu-id="a2716-103">To round the corners of a <xref:System.Windows.Media.RectangleGeometry>, set its <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> properties to a value greater than zero.</span></span> <span data-ttu-id="a2716-104">Je größer die Werte, desto runder die Ecken des Rechtecks.</span><span class="sxs-lookup"><span data-stu-id="a2716-104">The larger the values, the rounder the rectangle's corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2716-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2716-105">Example</span></span>  
 <span data-ttu-id="a2716-106">Das folgende Beispiel zeigt mehrere <xref:System.Windows.Media.RectangleGeometry> Objekte mit unterschiedlichen <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> und <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="a2716-106">The following example shows several <xref:System.Windows.Media.RectangleGeometry> objects with different <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> settings.</span></span> <span data-ttu-id="a2716-107">Die <xref:System.Windows.Media.RectangleGeometry> Objekte angezeigt werden, mithilfe von <xref:System.Windows.Shapes.Path> Elemente.</span><span class="sxs-lookup"><span data-stu-id="a2716-107">The <xref:System.Windows.Media.RectangleGeometry> objects are displayed using <xref:System.Windows.Shapes.Path> elements.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 <span data-ttu-id="a2716-108">![Rechtecke mit verschiedenen RadiusX&#47;RadiusY-Einstellungen](./media/graphicsmm-rounded.png "Graphicsmm_rounded")</span><span class="sxs-lookup"><span data-stu-id="a2716-108">![Rectangles with different RadiusX&#47;RadiusY settings](./media/graphicsmm-rounded.png "graphicsmm_rounded")</span></span>  
<span data-ttu-id="a2716-109">Rechtecke mit abgerundeten Ecken</span><span class="sxs-lookup"><span data-stu-id="a2716-109">Rectangles with Rounded Corners</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2716-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2716-110">See also</span></span>

- [<span data-ttu-id="a2716-111">Übersicht über die Geometrie</span><span class="sxs-lookup"><span data-stu-id="a2716-111">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="a2716-112">Erstellen einer zusammengesetzten Form</span><span class="sxs-lookup"><span data-stu-id="a2716-112">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="a2716-113">Erstellen einer Form mithilfe einer PathGeometry</span><span class="sxs-lookup"><span data-stu-id="a2716-113">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
