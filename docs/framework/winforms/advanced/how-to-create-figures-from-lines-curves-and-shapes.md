---
title: 'Vorgehensweise: Erstellen von Figuren aus Linien, Kurven und Formen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: c8cf7a7e08bed56fb704bba4e30ff369bc3fcf89
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64643469"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a><span data-ttu-id="f3ec3-102">Vorgehensweise: Erstellen von Figuren aus Linien, Kurven und Formen</span><span class="sxs-lookup"><span data-stu-id="f3ec3-102">How to: Create Figures from Lines, Curves, and Shapes</span></span>
<span data-ttu-id="f3ec3-103">Erstellen Sie zum Erstellen einer Figur eine <xref:System.Drawing.Drawing2D.GraphicsPath>, und rufen Sie anschließend die Methoden, wie z. B. <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> und <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, um primitive Typen in den Pfad hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-103">To create a figure, construct a <xref:System.Drawing.Drawing2D.GraphicsPath>, and then call methods, such as <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, to add primitives to the path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3ec3-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f3ec3-104">Example</span></span>  
 <span data-ttu-id="f3ec3-105">Die folgenden Codebeispiele erstellen Pfade, die Zahlen haben:</span><span class="sxs-lookup"><span data-stu-id="f3ec3-105">The following code examples create paths that have figures:</span></span>  
  
- <span data-ttu-id="f3ec3-106">Im erste Beispiel erstellt einen Pfad, der eine einzelne Figur enthält.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-106">The first example creates a path that has a single figure.</span></span> <span data-ttu-id="f3ec3-107">In der Abbildung besteht aus einem einzelnen Bogen. Der Bogen hat bei einem mittelpunktswinkel von –180 Grad gegen den Uhrzeigersinn in das Standardkoordinatensystem ist.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-107">The figure consists of a single arc. The arc has a sweep angle of –180 degrees, which is counterclockwise in the default coordinate system.</span></span>  
  
- <span data-ttu-id="f3ec3-108">Im zweite Beispiel wird einen Pfad, der zwei Abbildungen wurde erstellt.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-108">The second example creates a path that has two figures.</span></span> <span data-ttu-id="f3ec3-109">Die erste Figur ist einen Bogen, gefolgt von einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-109">The first figure is an arc followed by a line.</span></span> <span data-ttu-id="f3ec3-110">Die zweite Abbildung ist eine Zeile, gefolgt von einer Kurve, gefolgt von einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-110">The second figure is a line followed by a curve followed by a line.</span></span> <span data-ttu-id="f3ec3-111">Die erste Figur bleibt geöffnet, und die zweite Abbildung geschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-111">The first figure is left open, and the second figure is closed.</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f3ec3-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="f3ec3-112">Compiling the Code</span></span>  
 <span data-ttu-id="f3ec3-113">In den vorherigen Beispielen sind für die Verwendung mit Windows Forms konzipiert und erfordern <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="f3ec3-113">The previous examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ec3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3ec3-114">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [<span data-ttu-id="f3ec3-115">Erstellen und Zeichnen von Pfaden</span><span class="sxs-lookup"><span data-stu-id="f3ec3-115">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
- [<span data-ttu-id="f3ec3-116">Verwenden eines Stifts zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="f3ec3-116">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
