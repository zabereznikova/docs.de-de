---
title: 'Vorgehensweise: Festlegen der Farbe eines Stiftes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: dc067f5a131951bf3af7adc68e11b948d40fc0ca
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213414"
---
# <a name="how-to-set-the-color-of-a-pen"></a><span data-ttu-id="a96c9-102">Vorgehensweise: Festlegen der Farbe eines Stiftes</span><span class="sxs-lookup"><span data-stu-id="a96c9-102">How to: Set the Color of a Pen</span></span>
<span data-ttu-id="a96c9-103">In diesem Beispiel ändert sich die Farbe einer bereits vorhandenen <xref:System.Drawing.Pen> Objekt</span><span class="sxs-lookup"><span data-stu-id="a96c9-103">This example changes the color of a pre-existing <xref:System.Drawing.Pen> object</span></span>  
  
## <a name="example"></a><span data-ttu-id="a96c9-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a96c9-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a96c9-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="a96c9-105">Compiling the Code</span></span>  
 <span data-ttu-id="a96c9-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a96c9-106">This example requires:</span></span>  
  
-   <span data-ttu-id="a96c9-107">Ein <xref:System.Drawing.Pen> Objekt mit dem Namen `myPen`.</span><span class="sxs-lookup"><span data-stu-id="a96c9-107">A <xref:System.Drawing.Pen> object named `myPen`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a96c9-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="a96c9-108">Robust Programming</span></span>  
 <span data-ttu-id="a96c9-109">Rufen Sie <xref:System.Drawing.Pen.Dispose%2A> für Objekte, die Systemressourcen (z. B. <xref:System.Drawing.Pen> Objekte) nach deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="a96c9-109">You should call <xref:System.Drawing.Pen.Dispose%2A> on objects that consume system resources (such as <xref:System.Drawing.Pen> objects) after you are finished using them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a96c9-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a96c9-110">See also</span></span>

- <xref:System.Drawing.Pen>
- [<span data-ttu-id="a96c9-111">Erste Schritte mit der Grafikprogrammierung</span><span class="sxs-lookup"><span data-stu-id="a96c9-111">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="a96c9-112">Vorgehensweise: Erstellen eines Stifts</span><span class="sxs-lookup"><span data-stu-id="a96c9-112">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="a96c9-113">Verwenden eines Stiftes zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="a96c9-113">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="a96c9-114">Stifte, Linien und Rechtecke in GDI+</span><span class="sxs-lookup"><span data-stu-id="a96c9-114">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
