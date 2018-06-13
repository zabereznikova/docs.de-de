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
ms.openlocfilehash: b457e94acb334dc012f017090c63189de372592d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523922"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a><span data-ttu-id="9feca-102">Einschränken der Zeichenfläche in GDI+</span><span class="sxs-lookup"><span data-stu-id="9feca-102">Restricting the Drawing Surface in GDI+</span></span>
<span data-ttu-id="9feca-103">Clipping wird das Zeichnen für eine bestimmte Rechteck oder eine Region beschränkt.</span><span class="sxs-lookup"><span data-stu-id="9feca-103">Clipping involves restricting drawing to a certain rectangle or region.</span></span> <span data-ttu-id="9feca-104">Die folgende Abbildung zeigt die Zeichenfolge "Hello" in einer Region herzförmige abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="9feca-104">The following illustration shows the string "Hello" clipped to a heart-shaped region.</span></span>  
  
 <span data-ttu-id="9feca-105">![Eingeschränkte Zeichnungsoberfläche](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span><span class="sxs-lookup"><span data-stu-id="9feca-105">![Restricted Drawing Surface](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span></span>  
  
## <a name="clipping-with-regions"></a><span data-ttu-id="9feca-106">Clipping mit Bereichen</span><span class="sxs-lookup"><span data-stu-id="9feca-106">Clipping with Regions</span></span>  
 <span data-ttu-id="9feca-107">Regionen aus Pfaden konstruiert werden können, und Pfade können die Umrisse von Zeichenfolgen enthalten, damit Sie für das Clipping gegliederten Text verwenden können.</span><span class="sxs-lookup"><span data-stu-id="9feca-107">Regions can be constructed from paths, and paths can contain the outlines of strings, so you can use outlined text for clipping.</span></span> <span data-ttu-id="9feca-108">Die folgende Abbildung zeigt eine Reihe von konzentrischen Ellipsen, die das Innere einer Textzeichenfolge zugeschnitten.</span><span class="sxs-lookup"><span data-stu-id="9feca-108">The following illustration shows a set of concentric ellipses clipped to the interior of a string of text.</span></span>  
  
 <span data-ttu-id="9feca-109">![Eingeschränkte Zeichnungsoberfläche](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span><span class="sxs-lookup"><span data-stu-id="9feca-109">![Restricted Drawing Surface](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span></span>  
  
 <span data-ttu-id="9feca-110">Um Clipping zu zeichnen, erstellen Sie eine <xref:System.Drawing.Graphics> -Objekt, legen Sie seine <xref:System.Drawing.Graphics.Clip%2A> -Eigenschaft, und klicken Sie dann die Zeichnung Methoden, die gleichen aufgerufen <xref:System.Drawing.Graphics> Objekt:</span><span class="sxs-lookup"><span data-stu-id="9feca-110">To draw with clipping, create a <xref:System.Drawing.Graphics> object, set its <xref:System.Drawing.Graphics.Clip%2A> property, and then call the drawing methods of that same <xref:System.Drawing.Graphics> object:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#91](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a><span data-ttu-id="9feca-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9feca-111">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [<span data-ttu-id="9feca-112">Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="9feca-112">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="9feca-113">Verwenden von Bereichen</span><span class="sxs-lookup"><span data-stu-id="9feca-113">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)
