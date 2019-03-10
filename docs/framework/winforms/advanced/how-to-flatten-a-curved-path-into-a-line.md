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
ms.openlocfilehash: d4847124c7af2e0b35d6874f53b85be4891b22df
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711043"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="3ba3e-102">Vorgehensweise: Abflachen eines Kurvenpfads zu einer Linie</span><span class="sxs-lookup"><span data-stu-id="3ba3e-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="3ba3e-103">Ein <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt speichert eine Sequenz von Zeilen und Béziersplinekurven.</span><span class="sxs-lookup"><span data-stu-id="3ba3e-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="3ba3e-104">Sie können mehrere Typen von Kurven (Ellipsen, Bögen kardinale Splinekurven) in einen Pfad hinzufügen, aber jede Kurve wird in eine Béziersplinekurve konvertiert, bevor er im Pfad gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="3ba3e-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="3ba3e-105">Reduzieren einen Pfad besteht aus einzelnen Béziersplinekurve im Pfad in eine Sequenz von geraden Linien konvertieren.</span><span class="sxs-lookup"><span data-stu-id="3ba3e-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="3ba3e-106">Die folgende Abbildung zeigt einen Pfad an, vor und nach der Vereinfachung.</span><span class="sxs-lookup"><span data-stu-id="3ba3e-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="3ba3e-107">![Gerade Linien und Kurven](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="3ba3e-107">![Straight Lines and Curves](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="3ba3e-108">So vereinfachen Sie einen Pfad</span><span class="sxs-lookup"><span data-stu-id="3ba3e-108">To Flatten a Path</span></span>  
  
-   <span data-ttu-id="3ba3e-109">Rufen Sie die <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> Methode eine <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt.</span><span class="sxs-lookup"><span data-stu-id="3ba3e-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="3ba3e-110">Die <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> -Methode empfängt ein Flachheitsargument, das den maximalen Abstand zwischen den abgeflachten Pfad und den ursprünglichen Pfad angibt.</span><span class="sxs-lookup"><span data-stu-id="3ba3e-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ba3e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ba3e-111">See also</span></span>
- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [<span data-ttu-id="3ba3e-112">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="3ba3e-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="3ba3e-113">Erstellen und Zeichnen von Pfaden</span><span class="sxs-lookup"><span data-stu-id="3ba3e-113">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
