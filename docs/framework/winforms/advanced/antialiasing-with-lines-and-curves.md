---
title: Antialiasing bei Linien und Kurven
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b8552f185a93b688555dbcfab3da9d28d9bfde6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="antialiasing-with-lines-and-curves"></a><span data-ttu-id="94498-102">Antialiasing bei Linien und Kurven</span><span class="sxs-lookup"><span data-stu-id="94498-102">Antialiasing with Lines and Curves</span></span>
<span data-ttu-id="94498-103">Bei Verwendung von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] um eine Linie zeichnen, Sie geben Sie den Startpunkt und den Endpunkt der Linie, aber Sie müssen keine keine Informationen zu den einzelnen Pixel in der Zeile bereit.</span><span class="sxs-lookup"><span data-stu-id="94498-103">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, you provide the starting point and ending point of the line, but you do not have to provide any information about the individual pixels on the line.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="94498-104">funktioniert in Verbindung mit dem Bildschirmtreiber um zu bestimmen, welche Pixel aktiviert werden, werden um die Zeile auf die jeweiligen Ausgabegeräts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="94498-104"> works in conjunction with the display driver software to determine which pixels will be turned on to show the line on a particular display device.</span></span>  
  
## <a name="aliasing"></a><span data-ttu-id="94498-105">Aliasing</span><span class="sxs-lookup"><span data-stu-id="94498-105">Aliasing</span></span>  
 <span data-ttu-id="94498-106">Betrachten Sie die gerade rote Linie, die an dem Punkt (4, 2) auf den Punkt (16, 10) geht.</span><span class="sxs-lookup"><span data-stu-id="94498-106">Consider the straight red line that goes from the point (4, 2) to the point (16, 10).</span></span> <span data-ttu-id="94498-107">Angenommen Sie, das Koordinatensystem seinen Ursprung in der oberen linken Ecke hat und dass die Maßeinheit Pixel ist.</span><span class="sxs-lookup"><span data-stu-id="94498-107">Assume the coordinate system has its origin in the upper-left corner and that the unit of measure is the pixel.</span></span> <span data-ttu-id="94498-108">Darüber hinaus vorausgesetzt, dass die x-Achse nach rechts und die y-Achse Punkte nach unten.</span><span class="sxs-lookup"><span data-stu-id="94498-108">Also assume that the x-axis points to the right and the y-axis points down.</span></span> <span data-ttu-id="94498-109">Die folgende Abbildung zeigt eine vergrößerte Ansicht der die rote Linie, die auf einem mehrfarbigen Hintergrund gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="94498-109">The following illustration shows an enlarged view of the red line drawn on a multicolored background.</span></span>  
  
 <span data-ttu-id="94498-110">![Befehlszeile, ohne Antialiasing](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span><span class="sxs-lookup"><span data-stu-id="94498-110">![Line, no antialiasing](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span></span>  
  
 <span data-ttu-id="94498-111">Die roten Pixel, die zum Rendern der Zeile verwendeten sind nicht transparent.</span><span class="sxs-lookup"><span data-stu-id="94498-111">The red pixels used to render the line are opaque.</span></span> <span data-ttu-id="94498-112">Es gibt keine teilweise transparenten Pixel in der Zeile ein.</span><span class="sxs-lookup"><span data-stu-id="94498-112">There are no partially transparent pixels in the line.</span></span> <span data-ttu-id="94498-113">Diese Art der Darstellung der Linie gibt der Zeile einer gezackten Darstellung und sieht sich ähnlich wie eine Treppe.</span><span class="sxs-lookup"><span data-stu-id="94498-113">This type of line rendering gives the line a jagged appearance, and the line looks somewhat like a staircase.</span></span> <span data-ttu-id="94498-114">Dieses Verfahren, um eine Zeile mit einer Treppe darzustellen Aliasing aufgerufen wird. Treppe ist ein Alias für die theoretische Linie.</span><span class="sxs-lookup"><span data-stu-id="94498-114">This technique of representing a line with a staircase is called aliasing; the staircase is an alias for the theoretical line.</span></span>  
  
## <a name="antialiasing"></a><span data-ttu-id="94498-115">Antialiasing (Antialiasing)</span><span class="sxs-lookup"><span data-stu-id="94498-115">Antialiasing</span></span>  
 <span data-ttu-id="94498-116">Eine komplexere Technik zum Rendern einer Zeile wird teilweise transparente Pixel zusammen mit nicht transparenten Pixel.</span><span class="sxs-lookup"><span data-stu-id="94498-116">A more sophisticated technique for rendering a line involves using partially transparent pixels along with opaque pixels.</span></span> <span data-ttu-id="94498-117">Reines Rot Pixel festgelegt werden oder eine Mischung aus Rot und die Farbe des Hintergrunds, je nachdem, wie weit sie sind in der Zeile.</span><span class="sxs-lookup"><span data-stu-id="94498-117">Pixels are set to pure red, or to some blend of red and the background color, depending on how close they are to the line.</span></span> <span data-ttu-id="94498-118">Diese Art des Renderings Antialiasing aufgerufen wird und führt zu einer Zeile, die als glatter Tabellenlayout wahrgenommen.</span><span class="sxs-lookup"><span data-stu-id="94498-118">This type of rendering is called antialiasing and results in a line that the human eye perceives as more smooth.</span></span> <span data-ttu-id="94498-119">Die folgende Abbildung zeigt, wie bestimmte Pixel mit Hintergrund aus, um eine Zeile mit Antialiasing erzeugen gemischt werden.</span><span class="sxs-lookup"><span data-stu-id="94498-119">The following illustration shows how certain pixels are blended with the background to produce an antialiased line.</span></span>  
  
 <span data-ttu-id="94498-120">![Antialiasing bei einer Linie](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span><span class="sxs-lookup"><span data-stu-id="94498-120">![Antialiasing a Line](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span></span>  
  
 <span data-ttu-id="94498-121">Antialiasing (Antialiasing), das auch als Glättung kann auch auf Kurven angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="94498-121">Antialiasing, also called smoothing, can also be applied to curves.</span></span> <span data-ttu-id="94498-122">Die folgende Abbildung zeigt eine vergrößerte Ansicht einer geglätteten Ellipse.</span><span class="sxs-lookup"><span data-stu-id="94498-122">The following illustration shows an enlarged view of a smoothed ellipse.</span></span>  
  
 <span data-ttu-id="94498-123">![Antialiasing bei Kurven](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span><span class="sxs-lookup"><span data-stu-id="94498-123">![Antialiasing Curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span></span>  
  
 <span data-ttu-id="94498-124">Die folgende Abbildung zeigt die gleiche Ellipse in der Originalgröße an, ohne Antialiasing (Antialiasing) und einmal mit Antialiasing (Antialiasing).</span><span class="sxs-lookup"><span data-stu-id="94498-124">The following illustration shows the same ellipse in its actual size, once without antialiasing and once with antialiasing.</span></span>  
  
 <span data-ttu-id="94498-125">![Antialiasingbeispiel](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span><span class="sxs-lookup"><span data-stu-id="94498-125">![Antialiasing example](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span></span>  
  
 <span data-ttu-id="94498-126">Zum Zeichnen von Linien und Kurven mit Antialiasing, erstellen Sie eine Instanz von der <xref:System.Drawing.Graphics> Klasse, und legen seine <xref:System.Drawing.Graphics.SmoothingMode%2A> Eigenschaft <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> oder <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span><span class="sxs-lookup"><span data-stu-id="94498-126">To draw lines and curves that use antialiasing, create an instance of the <xref:System.Drawing.Graphics> class and set its <xref:System.Drawing.Graphics.SmoothingMode%2A> property to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> or <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span></span> <span data-ttu-id="94498-127">Dann rufen Sie eine der Zeichnung Methoden, die gleichen <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="94498-127">Then call one of the drawing methods of that same <xref:System.Drawing.Graphics> class.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a><span data-ttu-id="94498-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94498-128">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>  
 [<span data-ttu-id="94498-129">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="94498-129">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="94498-130">Gewusst wie: Verwenden der Bildkantenglättung mit Text</span><span class="sxs-lookup"><span data-stu-id="94498-130">How to: Use Antialiasing with Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)
