---
title: Verwenden der globalen Transformation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
ms.openlocfilehash: f40d7e8cb814344365e8b88c2659751903b79d77
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969142"
---
# <a name="using-the-world-transformation"></a><span data-ttu-id="2c57d-102">Verwenden der globalen Transformation</span><span class="sxs-lookup"><span data-stu-id="2c57d-102">Using the World Transformation</span></span>
<span data-ttu-id="2c57d-103">Die globale Transformation ist eine Eigenschaft der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="2c57d-103">The world transformation is a property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="2c57d-104">Die Zahlen, die die globale Transformation angeben, befinden sich in einem <xref:System.Drawing.Drawing2D.Matrix> -Objekt, das eine 3 x 3-Matrix darstellt.</span><span class="sxs-lookup"><span data-stu-id="2c57d-104">The numbers that specify the world transformation are stored in a <xref:System.Drawing.Drawing2D.Matrix> object, which represents a 3×3 matrix.</span></span> <span data-ttu-id="2c57d-105">Die <xref:System.Drawing.Drawing2D.Matrix> und <xref:System.Drawing.Graphics> Klassen verfügen über mehrere Methoden zum Festlegen der Zahlen in die globale Transformationsmatrix.</span><span class="sxs-lookup"><span data-stu-id="2c57d-105">The <xref:System.Drawing.Drawing2D.Matrix> and <xref:System.Drawing.Graphics> classes have several methods for setting the numbers in the world transformation matrix.</span></span>  
  
## <a name="different-types-of-transformations"></a><span data-ttu-id="2c57d-106">Verschiedene Arten von Transformationen</span><span class="sxs-lookup"><span data-stu-id="2c57d-106">Different Types of Transformations</span></span>  
 <span data-ttu-id="2c57d-107">Im folgenden Beispiel wird der Code zuerst erstellt ein Rechteck 50 x 50, und sucht er am Ursprung (0, 0).</span><span class="sxs-lookup"><span data-stu-id="2c57d-107">In the following example, the code first creates a 50×50 rectangle and locates it at the origin (0, 0).</span></span> <span data-ttu-id="2c57d-108">Der Ursprung befindet sich in der oberen linken Ecke des Clientbereichs.</span><span class="sxs-lookup"><span data-stu-id="2c57d-108">The origin is at the upper-left corner of the client area.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 <span data-ttu-id="2c57d-109">Der folgende Code gilt eine Skalierungstransformation, die erweitert das Rechteck mit einem Faktor von 1,75 in X-Richtung und verkleinert das Rechteck um den Faktor 0,5 in y-Richtung:</span><span class="sxs-lookup"><span data-stu-id="2c57d-109">The following code applies a scaling transformation that expands the rectangle by a factor of 1.75 in the x direction and shrinks the rectangle by a factor of 0.5 in the y direction:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 <span data-ttu-id="2c57d-110">Das Ergebnis ist ein Rechteck, mehr in Richtung der x-Achse und die y-Richtung kürzer als das Original.</span><span class="sxs-lookup"><span data-stu-id="2c57d-110">The result is a rectangle that is longer in the x direction and shorter in the y direction than the original.</span></span>  
  
 <span data-ttu-id="2c57d-111">Um das Rechteck, anstelle es zu drehen, verwenden Sie den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="2c57d-111">To rotate the rectangle instead of scaling it, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 <span data-ttu-id="2c57d-112">Um das Rechteck zu übersetzen, verwenden Sie den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="2c57d-112">To translate the rectangle, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="2c57d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c57d-113">See also</span></span>

- <xref:System.Drawing.Drawing2D.Matrix>
- [<span data-ttu-id="2c57d-114">Koordinatensysteme und Transformationen</span><span class="sxs-lookup"><span data-stu-id="2c57d-114">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="2c57d-115">Verwenden von Transformationen in Managed GDI+</span><span class="sxs-lookup"><span data-stu-id="2c57d-115">Using Transformations in Managed GDI+</span></span>](using-transformations-in-managed-gdi.md)
