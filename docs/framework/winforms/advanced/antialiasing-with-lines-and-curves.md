---
title: Antialiasing bei Linien und Kurven
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
ms.openlocfilehash: cbc9033f18f1ab255862c8f8e2891aa9b68cf8d6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078497"
---
# <a name="antialiasing-with-lines-and-curves"></a><span data-ttu-id="005f7-102">Antialiasing bei Linien und Kurven</span><span class="sxs-lookup"><span data-stu-id="005f7-102">Antialiasing with Lines and Curves</span></span>
<span data-ttu-id="005f7-103">Bei Verwendung von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] um eine Linie zu zeichnen, Sie geben Sie den Startpunkt und Endpunkt der Linie, aber Sie müssen keine Informationen zu den einzelnen Pixel in der Zeile zu bieten.</span><span class="sxs-lookup"><span data-stu-id="005f7-103">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, you provide the starting point and ending point of the line, but you do not have to provide any information about the individual pixels on the line.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="005f7-104">funktioniert in Verbindung mit dem Bildschirmtreiber um zu bestimmen, welche Pixel aktiviert werden, werden um die Zeile in der jeweiligen Ausgabegeräts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="005f7-104">works in conjunction with the display driver software to determine which pixels will be turned on to show the line on a particular display device.</span></span>  
  
## <a name="aliasing"></a><span data-ttu-id="005f7-105">Aliasing</span><span class="sxs-lookup"><span data-stu-id="005f7-105">Aliasing</span></span>  
 <span data-ttu-id="005f7-106">Erwägen Sie die gerade rote Linie, die ab dem Punkt ("4", "2") gesendet wird, zu dem Punkt ("16", "10").</span><span class="sxs-lookup"><span data-stu-id="005f7-106">Consider the straight red line that goes from the point (4, 2) to the point (16, 10).</span></span> <span data-ttu-id="005f7-107">Angenommen Sie das Koordinatensystem seinen Ursprung in der oberen linken Ecke hat und die Maßeinheit ist Pixel.</span><span class="sxs-lookup"><span data-stu-id="005f7-107">Assume the coordinate system has its origin in the upper-left corner and that the unit of measure is the pixel.</span></span> <span data-ttu-id="005f7-108">Darüber hinaus vorausgesetzt, dass die x-Achse nach rechts und die Punkte für die y-Achse nach unten zeigt.</span><span class="sxs-lookup"><span data-stu-id="005f7-108">Also assume that the x-axis points to the right and the y-axis points down.</span></span> <span data-ttu-id="005f7-109">Die folgende Abbildung zeigt eine vergrößerte Ansicht der roten Linie vor einem Hintergrund mehrfarbige.</span><span class="sxs-lookup"><span data-stu-id="005f7-109">The following illustration shows an enlarged view of the red line drawn on a multicolored background.</span></span>  
  
 <span data-ttu-id="005f7-110">![Zeile, die ohne Antialiasing](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span><span class="sxs-lookup"><span data-stu-id="005f7-110">![Line, no antialiasing](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span></span>  
  
 <span data-ttu-id="005f7-111">Die roten Pixel verwendet, um die Linie zu rendern sind nicht transparent.</span><span class="sxs-lookup"><span data-stu-id="005f7-111">The red pixels used to render the line are opaque.</span></span> <span data-ttu-id="005f7-112">Es gibt keine teilweise transparente Pixel in der Zeile.</span><span class="sxs-lookup"><span data-stu-id="005f7-112">There are no partially transparent pixels in the line.</span></span> <span data-ttu-id="005f7-113">Diese Art der Darstellung der Linie gibt der Zeile einer gezackten Darstellung, und die Zeile ähnelt einer Treppe.</span><span class="sxs-lookup"><span data-stu-id="005f7-113">This type of line rendering gives the line a jagged appearance, and the line looks somewhat like a staircase.</span></span> <span data-ttu-id="005f7-114">Dieses Verfahren für die Darstellung einer Linie mit einer Treppe wird Aliasing bezeichnet. der Treppe ist ein Alias für der theoretischen Linie.</span><span class="sxs-lookup"><span data-stu-id="005f7-114">This technique of representing a line with a staircase is called aliasing; the staircase is an alias for the theoretical line.</span></span>  
  
## <a name="antialiasing"></a><span data-ttu-id="005f7-115">Antialiasing</span><span class="sxs-lookup"><span data-stu-id="005f7-115">Antialiasing</span></span>  
 <span data-ttu-id="005f7-116">Eine anspruchsvollere Technik für das Rendern einer Zeile umfasst die teilweise transparente Pixel zusammen mit nicht transparenten Pixel.</span><span class="sxs-lookup"><span data-stu-id="005f7-116">A more sophisticated technique for rendering a line involves using partially transparent pixels along with opaque pixels.</span></span> <span data-ttu-id="005f7-117">Pixel auf reine Rot festgelegt, oder eine Mischung aus Red Team und die Farbe des Hintergrunds, je nachdem, wie weit sie sind in der Zeile.</span><span class="sxs-lookup"><span data-stu-id="005f7-117">Pixels are set to pure red, or to some blend of red and the background color, depending on how close they are to the line.</span></span> <span data-ttu-id="005f7-118">Dieser Typ, der Rendering Antialiasing wird aufgerufen, und führt eine Linie, die das menschliche Auge als glatter wahrgenommen.</span><span class="sxs-lookup"><span data-stu-id="005f7-118">This type of rendering is called antialiasing and results in a line that the human eye perceives as more smooth.</span></span> <span data-ttu-id="005f7-119">Die folgende Abbildung zeigt, wie bestimmte Pixel vermischt werden, mit dem Hintergrund, um eine Zeile mit Antialiasing zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="005f7-119">The following illustration shows how certain pixels are blended with the background to produce an antialiased line.</span></span>  
  
 <span data-ttu-id="005f7-120">![Antialiasing bei einer Linie](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span><span class="sxs-lookup"><span data-stu-id="005f7-120">![Antialiasing a Line](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span></span>  
  
 <span data-ttu-id="005f7-121">Antialiasing, das auch als Glättung kann auch auf Kurven angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="005f7-121">Antialiasing, also called smoothing, can also be applied to curves.</span></span> <span data-ttu-id="005f7-122">Die folgende Abbildung zeigt eine vergrößerte Ansicht einer geglätteten Ellipse.</span><span class="sxs-lookup"><span data-stu-id="005f7-122">The following illustration shows an enlarged view of a smoothed ellipse.</span></span>  
  
 <span data-ttu-id="005f7-123">![Antialiasing bei Kurven](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span><span class="sxs-lookup"><span data-stu-id="005f7-123">![Antialiasing Curves](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span></span>  
  
 <span data-ttu-id="005f7-124">Die folgende Abbildung zeigt die gleiche Ellipse in die tatsächliche Größe ohne Antialiasing und einmal mit Antialiasing.</span><span class="sxs-lookup"><span data-stu-id="005f7-124">The following illustration shows the same ellipse in its actual size, once without antialiasing and once with antialiasing.</span></span>  
  
 <span data-ttu-id="005f7-125">![Antialiasingbeispiel](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span><span class="sxs-lookup"><span data-stu-id="005f7-125">![Antialiasing example](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span></span>  
  
 <span data-ttu-id="005f7-126">Um Linien und Kurven mit Antialiasing zu zeichnen, erstellen Sie eine Instanz des der <xref:System.Drawing.Graphics> Klasse und legen Sie dessen <xref:System.Drawing.Graphics.SmoothingMode%2A> Eigenschaft <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> oder <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span><span class="sxs-lookup"><span data-stu-id="005f7-126">To draw lines and curves that use antialiasing, create an instance of the <xref:System.Drawing.Graphics> class and set its <xref:System.Drawing.Graphics.SmoothingMode%2A> property to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> or <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span></span> <span data-ttu-id="005f7-127">Dann rufen Sie eine der Zeichenmethoden der, die gleichen <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="005f7-127">Then call one of the drawing methods of that same <xref:System.Drawing.Graphics> class.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#81](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a><span data-ttu-id="005f7-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="005f7-128">See also</span></span>

- <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>
- [<span data-ttu-id="005f7-129">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="005f7-129">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="005f7-130">Vorgehensweise: Verwenden der Bildkantenglättung mit Text</span><span class="sxs-lookup"><span data-stu-id="005f7-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)
