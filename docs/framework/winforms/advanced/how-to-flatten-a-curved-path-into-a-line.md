---
title: 'Vorgehensweise: Abflachen eines Kurvenpfads zu einer Linie'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: a151b4244e14d3704fd5fa1c55de92211981232f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781368"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="9eb4c-102">Vorgehensweise: Abflachen eines Kurvenpfads zu einer Linie</span><span class="sxs-lookup"><span data-stu-id="9eb4c-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="9eb4c-103">Ein <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt speichert eine Sequenz von Zeilen und Béziersplinekurven.</span><span class="sxs-lookup"><span data-stu-id="9eb4c-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="9eb4c-104">Sie können mehrere Typen von Kurven (Ellipsen, Bögen kardinale Splinekurven) in einen Pfad hinzufügen, aber jede Kurve wird in eine Béziersplinekurve konvertiert, bevor er im Pfad gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="9eb4c-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="9eb4c-105">Reduzieren einen Pfad besteht aus einzelnen Béziersplinekurve im Pfad in eine Sequenz von geraden Linien konvertieren.</span><span class="sxs-lookup"><span data-stu-id="9eb4c-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="9eb4c-106">Die folgende Abbildung zeigt einen Pfad an, vor und nach der Vereinfachung.</span><span class="sxs-lookup"><span data-stu-id="9eb4c-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="9eb4c-107">![Gerade Linien und Kurven](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="9eb4c-107">![Straight Lines and Curves](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="9eb4c-108">So vereinfachen Sie einen Pfad</span><span class="sxs-lookup"><span data-stu-id="9eb4c-108">To Flatten a Path</span></span>  
  
- <span data-ttu-id="9eb4c-109">Rufen Sie die <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> Methode eine <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt.</span><span class="sxs-lookup"><span data-stu-id="9eb4c-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="9eb4c-110">Die <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> -Methode empfängt ein Flachheitsargument, das den maximalen Abstand zwischen den abgeflachten Pfad und den ursprünglichen Pfad angibt.</span><span class="sxs-lookup"><span data-stu-id="9eb4c-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eb4c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9eb4c-111">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [<span data-ttu-id="9eb4c-112">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="9eb4c-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="9eb4c-113">Erstellen und Zeichnen von Pfaden</span><span class="sxs-lookup"><span data-stu-id="9eb4c-113">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
