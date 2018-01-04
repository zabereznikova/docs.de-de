---
title: Verwenden der globalen Transformation
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
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e8599f2e154e05fd2d43b094041989c4a3a5dbc0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-world-transformation"></a><span data-ttu-id="d97f6-102">Verwenden der globalen Transformation</span><span class="sxs-lookup"><span data-stu-id="d97f6-102">Using the World Transformation</span></span>
<span data-ttu-id="d97f6-103">Die globale Transformation ist eine Eigenschaft der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="d97f6-103">The world transformation is a property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="d97f6-104">Die Zahlen, die die globale Transformation angeben befinden sich einem <xref:System.Drawing.Drawing2D.Matrix> Objekt, das eine 3 x 3-Matrix darstellt.</span><span class="sxs-lookup"><span data-stu-id="d97f6-104">The numbers that specify the world transformation are stored in a <xref:System.Drawing.Drawing2D.Matrix> object, which represents a 3×3 matrix.</span></span> <span data-ttu-id="d97f6-105">Die <xref:System.Drawing.Drawing2D.Matrix> und <xref:System.Drawing.Graphics> Klassen verfügen über mehrere Methoden zum Festlegen der Zahlen in die globale Transformationsmatrix.</span><span class="sxs-lookup"><span data-stu-id="d97f6-105">The <xref:System.Drawing.Drawing2D.Matrix> and <xref:System.Drawing.Graphics> classes have several methods for setting the numbers in the world transformation matrix.</span></span>  
  
## <a name="different-types-of-transformations"></a><span data-ttu-id="d97f6-106">Verschiedene Arten von Transformationen</span><span class="sxs-lookup"><span data-stu-id="d97f6-106">Different Types of Transformations</span></span>  
 <span data-ttu-id="d97f6-107">Im folgenden Beispiel wird der Code zuerst erstellt ein Rechteck, 50 x 50, und sucht er am ursprünglichen Speicherort (0, 0).</span><span class="sxs-lookup"><span data-stu-id="d97f6-107">In the following example, the code first creates a 50×50 rectangle and locates it at the origin (0, 0).</span></span> <span data-ttu-id="d97f6-108">Der Ursprung befindet sich in der oberen linken Ecke des Clientbereichs.</span><span class="sxs-lookup"><span data-stu-id="d97f6-108">The origin is at the upper-left corner of the client area.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 <span data-ttu-id="d97f6-109">Der folgende Code wendet eine Skalierungstransformation, die das Rechteck mit dem Faktor 1,75 entlang der x-Achse an erweitert und verkleinert das Rechteck mit einem Faktor von 0,5 entlang der y-Achse an:</span><span class="sxs-lookup"><span data-stu-id="d97f6-109">The following code applies a scaling transformation that expands the rectangle by a factor of 1.75 in the x direction and shrinks the rectangle by a factor of 0.5 in the y direction:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 <span data-ttu-id="d97f6-110">Das Ergebnis ist ein Rechteck, das länger in X-Richtung und in der y-Richtung kürzer ist als die ursprüngliche ist.</span><span class="sxs-lookup"><span data-stu-id="d97f6-110">The result is a rectangle that is longer in the x direction and shorter in the y direction than the original.</span></span>  
  
 <span data-ttu-id="d97f6-111">Um das Rechteck statt Skalierung zu wechseln, verwenden Sie den folgenden Code ein:</span><span class="sxs-lookup"><span data-stu-id="d97f6-111">To rotate the rectangle instead of scaling it, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 <span data-ttu-id="d97f6-112">Um das Rechteck zu übersetzen, verwenden Sie den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="d97f6-112">To translate the rectangle, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="d97f6-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d97f6-113">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.Matrix>  
 [<span data-ttu-id="d97f6-114">Koordinatensysteme und Transformationen</span><span class="sxs-lookup"><span data-stu-id="d97f6-114">Coordinate Systems and Transformations</span></span>](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [<span data-ttu-id="d97f6-115">Verwenden von Transformationen in Managed GDI+</span><span class="sxs-lookup"><span data-stu-id="d97f6-115">Using Transformations in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
