---
title: Einschränken der Zeichenfläche in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
ms.openlocfilehash: d0508166f905b45789ce638b03d0747dd6fa904e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61672625"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a><span data-ttu-id="e4606-102">Einschränken der Zeichenfläche in GDI+</span><span class="sxs-lookup"><span data-stu-id="e4606-102">Restricting the Drawing Surface in GDI+</span></span>
<span data-ttu-id="e4606-103">Clipping wird Zeichnung auf ein bestimmtes Rechteck oder Region beschränkt.</span><span class="sxs-lookup"><span data-stu-id="e4606-103">Clipping involves restricting drawing to a certain rectangle or region.</span></span> <span data-ttu-id="e4606-104">Die folgende Abbildung zeigt die Zeichenfolge "Hello" in einer Region Kern gestalteten abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="e4606-104">The following illustration shows the string "Hello" clipped to a heart-shaped region.</span></span>  
  
 <span data-ttu-id="e4606-105">![Eingeschränkte Zeichnungsoberfläche](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span><span class="sxs-lookup"><span data-stu-id="e4606-105">![Restricted Drawing Surface](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span></span>  
  
## <a name="clipping-with-regions"></a><span data-ttu-id="e4606-106">Clipping mit Bereichen</span><span class="sxs-lookup"><span data-stu-id="e4606-106">Clipping with Regions</span></span>  
 <span data-ttu-id="e4606-107">Regionen können erstellt werden, aus Pfaden und Pfade können die Umrisse von Zeichenfolgen enthalten, sodass Sie Text mit Kontur für das Clipping verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e4606-107">Regions can be constructed from paths, and paths can contain the outlines of strings, so you can use outlined text for clipping.</span></span> <span data-ttu-id="e4606-108">Die folgende Abbildung zeigt eine Reihe von konzentrischen Ellipsen, die auf das Innere einer Textzeichenfolge abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="e4606-108">The following illustration shows a set of concentric ellipses clipped to the interior of a string of text.</span></span>  
  
 <span data-ttu-id="e4606-109">![Eingeschränkte Zeichnungsoberfläche](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span><span class="sxs-lookup"><span data-stu-id="e4606-109">![Restricted Drawing Surface](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span></span>  
  
 <span data-ttu-id="e4606-110">Um mit Clipping zu zeichnen, erstellen eine <xref:System.Drawing.Graphics> -Objekts seine <xref:System.Drawing.Graphics.Clip%2A> -Eigenschaft, und rufen Sie dann den Zeichenmethoden der, die gleichen <xref:System.Drawing.Graphics> Objekt:</span><span class="sxs-lookup"><span data-stu-id="e4606-110">To draw with clipping, create a <xref:System.Drawing.Graphics> object, set its <xref:System.Drawing.Graphics.Clip%2A> property, and then call the drawing methods of that same <xref:System.Drawing.Graphics> object:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#91](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a><span data-ttu-id="e4606-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4606-111">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [<span data-ttu-id="e4606-112">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="e4606-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="e4606-113">Verwenden von Bereichen</span><span class="sxs-lookup"><span data-stu-id="e4606-113">Using Regions</span></span>](using-regions.md)
