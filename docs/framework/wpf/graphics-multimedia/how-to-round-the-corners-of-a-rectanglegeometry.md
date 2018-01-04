---
title: 'Gewusst wie: Abrunden der Ecken einer "RectangleGeometry"'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 92a51b3c610d3755583f8a39314f45d3980ee1bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a><span data-ttu-id="8fbf4-102">Gewusst wie: Abrunden der Ecken einer "RectangleGeometry"</span><span class="sxs-lookup"><span data-stu-id="8fbf4-102">How to: Round the Corners of a RectangleGeometry</span></span>
<span data-ttu-id="8fbf4-103">Um das Abrunden der Ecken des eine <xref:System.Windows.Media.RectangleGeometry>legen seine <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> und <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> Eigenschaften auf einen Wert größer als 0 (null).</span><span class="sxs-lookup"><span data-stu-id="8fbf4-103">To round the corners of a <xref:System.Windows.Media.RectangleGeometry>, set its <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> properties to a value greater than zero.</span></span> <span data-ttu-id="8fbf4-104">Je größer die Werte, desto runder die Ecken des Rechtecks.</span><span class="sxs-lookup"><span data-stu-id="8fbf4-104">The larger the values, the rounder the rectangle's corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fbf4-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8fbf4-105">Example</span></span>  
 <span data-ttu-id="8fbf4-106">Das folgende Beispiel zeigt mehrere <xref:System.Windows.Media.RectangleGeometry> Objekte mit unterschiedlichen <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> und <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="8fbf4-106">The following example shows several <xref:System.Windows.Media.RectangleGeometry> objects with different <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> settings.</span></span> <span data-ttu-id="8fbf4-107">Die <xref:System.Windows.Media.RectangleGeometry> Objekte angezeigt werden, mit <xref:System.Windows.Shapes.Path> Elemente.</span><span class="sxs-lookup"><span data-stu-id="8fbf4-107">The <xref:System.Windows.Media.RectangleGeometry> objects are displayed using <xref:System.Windows.Shapes.Path> elements.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 <span data-ttu-id="8fbf4-108">![Rechtecke mit verschiedenen RadiusX &#47; RadiusY-Einstellungen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "Graphicsmm_rounded")</span><span class="sxs-lookup"><span data-stu-id="8fbf4-108">![Rectangles with different RadiusX&#47;RadiusY settings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")</span></span>  
<span data-ttu-id="8fbf4-109">Rechtecke mit abgerundeten Ecken</span><span class="sxs-lookup"><span data-stu-id="8fbf4-109">Rectangles with Rounded Corners</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fbf4-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fbf4-110">See Also</span></span>  
 [<span data-ttu-id="8fbf4-111">Übersicht über Geometrien</span><span class="sxs-lookup"><span data-stu-id="8fbf4-111">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="8fbf4-112">Erstellen einer zusammengesetzten Form</span><span class="sxs-lookup"><span data-stu-id="8fbf4-112">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="8fbf4-113">Erstellen einer Form mithilfe von PathGeometry</span><span class="sxs-lookup"><span data-stu-id="8fbf4-113">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
