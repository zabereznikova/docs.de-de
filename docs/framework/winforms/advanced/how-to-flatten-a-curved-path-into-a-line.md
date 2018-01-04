---
title: 'Gewusst wie: Abflachen eines Kurvenpfads zu einer Linie'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 334fc0fee7166f8f8c5c1db61d3b9e370da72f87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="c4d51-102">Gewusst wie: Abflachen eines Kurvenpfads zu einer Linie</span><span class="sxs-lookup"><span data-stu-id="c4d51-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="c4d51-103">Ein <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt eine Sequenz von Linien und Bézier-Splines speichert.</span><span class="sxs-lookup"><span data-stu-id="c4d51-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="c4d51-104">Sie können mehrere Typen von Kurven (Ellipsen, Bögen, kardinale Splines) hinzufügen, um einen Pfad, aber jede Kurve wird in eine Bézier-Spline konvertiert, vor dem Speichern im Pfad.</span><span class="sxs-lookup"><span data-stu-id="c4d51-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="c4d51-105">Reduzieren einen Pfad besteht aus einzelnen Bézier-Splines in den Pfad in eine Sequenz von gerade Linien konvertieren.</span><span class="sxs-lookup"><span data-stu-id="c4d51-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="c4d51-106">Die folgende Abbildung zeigt einen Pfad vor und nach vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="c4d51-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="c4d51-107">![Gerade Linien und Kurven](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="c4d51-107">![Straight Lines and Curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="c4d51-108">So vereinfachen Sie einen Pfad</span><span class="sxs-lookup"><span data-stu-id="c4d51-108">To Flatten a Path</span></span>  
  
-   <span data-ttu-id="c4d51-109">Rufen Sie die <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> Methode von einer <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt.</span><span class="sxs-lookup"><span data-stu-id="c4d51-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="c4d51-110">Die <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> -Methode erhält ein Flachheitsargument, der den maximalen Abstand zwischen dem vereinfachten und der ursprüngliche Pfad angibt.</span><span class="sxs-lookup"><span data-stu-id="c4d51-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4d51-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4d51-111">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 [<span data-ttu-id="c4d51-112">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="c4d51-112">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="c4d51-113">Erstellen und Zeichnen von Pfaden</span><span class="sxs-lookup"><span data-stu-id="c4d51-113">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
