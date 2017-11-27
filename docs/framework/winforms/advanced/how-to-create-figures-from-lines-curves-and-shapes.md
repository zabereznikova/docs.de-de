---
title: 'Gewusst wie: Erstellen von Figuren aus Linien, Kurven und Formen'
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
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b382e0e1a627d7f61ce8ac664ac47d98c3725cad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a><span data-ttu-id="d4e70-102">Gewusst wie: Erstellen von Figuren aus Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="d4e70-102">How to: Create Figures from Lines, Curves, and Shapes</span></span>
<span data-ttu-id="d4e70-103">Um eine Figur zu erstellen, erstellen Sie eine <xref:System.Drawing.Drawing2D.GraphicsPath>, und rufen Sie Methoden, wie z. B. <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> und <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, um den Pfad Primitive hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d4e70-103">To create a figure, construct a <xref:System.Drawing.Drawing2D.GraphicsPath>, and then call methods, such as <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, to add primitives to the path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4e70-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d4e70-104">Example</span></span>  
 <span data-ttu-id="d4e70-105">Die folgenden Codebeispiele erstellen Pfade, die Formen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="d4e70-105">The following code examples create paths that have figures:</span></span>  
  
-   <span data-ttu-id="d4e70-106">Im erste Beispiel erstellt einen Pfad mit einer einzelnen Abbildung.</span><span class="sxs-lookup"><span data-stu-id="d4e70-106">The first example creates a path that has a single figure.</span></span> <span data-ttu-id="d4e70-107">Die Abbildung besteht aus einem einzelnen Bogen. Der Bogen hat bei einem mittelpunktswinkel von –180 Grad, also in der Standardeinstellung Koordinatensystem gegen den Uhrzeigersinn.</span><span class="sxs-lookup"><span data-stu-id="d4e70-107">The figure consists of a single arc. The arc has a sweep angle of –180 degrees, which is counterclockwise in the default coordinate system.</span></span>  
  
-   <span data-ttu-id="d4e70-108">Im zweite Beispiel wird einen Pfad, der zwei Zahlen wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="d4e70-108">The second example creates a path that has two figures.</span></span> <span data-ttu-id="d4e70-109">Die erste Abbildung ist einen Bogen, gefolgt von einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="d4e70-109">The first figure is an arc followed by a line.</span></span> <span data-ttu-id="d4e70-110">Die zweite Abbildung ist eine Zeile, gefolgt von einer Kurve, gefolgt von einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="d4e70-110">The second figure is a line followed by a curve followed by a line.</span></span> <span data-ttu-id="d4e70-111">In der ersten Abbildung bleibt geöffnet, und die zweite Abbildung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="d4e70-111">The first figure is left open, and the second figure is closed.</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d4e70-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d4e70-112">Compiling the Code</span></span>  
 <span data-ttu-id="d4e70-113">In den vorherigen Beispielen sind für die Verwendung mit Windows Forms konzipiert und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="d4e70-113">The previous examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4e70-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4e70-114">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [<span data-ttu-id="d4e70-115">Erstellen und Zeichnen von Pfaden</span><span class="sxs-lookup"><span data-stu-id="d4e70-115">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)  
 [<span data-ttu-id="d4e70-116">Verwenden eines Stifts zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="d4e70-116">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
