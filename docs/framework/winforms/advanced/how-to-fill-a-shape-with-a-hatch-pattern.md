---
title: 'Gewusst wie: Ausfüllen einer Form mit einer Schraffur'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: b80708f0ce722b1809fe49190639231e7e4c8329
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320049"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a><span data-ttu-id="2ef3e-102">Gewusst wie: Ausfüllen einer Form mit einer Schraffur</span><span class="sxs-lookup"><span data-stu-id="2ef3e-102">How to: Fill a Shape with a Hatch Pattern</span></span>
<span data-ttu-id="2ef3e-103">Ein Schraffurmuster wird aus zwei Farben erstellt: eine für den Hintergrund und eine für die Linien, die das Muster über den Hintergrund bilden.</span><span class="sxs-lookup"><span data-stu-id="2ef3e-103">A hatch pattern is made from two colors: one for the background and one for the lines that form the pattern over the background.</span></span> <span data-ttu-id="2ef3e-104">Um eine geschlossene Form mit einem Schraffurmuster zu füllen, verwenden Sie ein <xref:System.Drawing.Drawing2D.HatchBrush>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="2ef3e-104">To fill a closed shape with a hatch pattern, use a <xref:System.Drawing.Drawing2D.HatchBrush> object.</span></span> <span data-ttu-id="2ef3e-105">Im folgenden Beispiel wird veranschaulicht, wie Sie eine Ellipse mit einem Schraffurmuster ausfüllen:</span><span class="sxs-lookup"><span data-stu-id="2ef3e-105">The following example demonstrates how to fill an ellipse with a hatch pattern:</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ef3e-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ef3e-106">Example</span></span>  
 <span data-ttu-id="2ef3e-107">Der <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A>-Konstruktor benötigt drei Argumente: die Schraffurart, die Farbe der schraffurzeile und die Farbe des Hintergrunds.</span><span class="sxs-lookup"><span data-stu-id="2ef3e-107">The <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor takes three arguments: the hatch style, the color of the hatch line, and the color of the background.</span></span> <span data-ttu-id="2ef3e-108">Das schraffurargumentgument kann ein beliebiger Wert aus der <xref:System.Drawing.Drawing2D.HatchStyle>-Enumeration sein.</span><span class="sxs-lookup"><span data-stu-id="2ef3e-108">The hatch style argument can be any value from the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration.</span></span> <span data-ttu-id="2ef3e-109">In der <xref:System.Drawing.Drawing2D.HatchStyle>-Enumeration sind mehr als 50 Elemente vorhanden. Einige dieser Elemente sind in der folgenden Liste aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="2ef3e-109">There are more than fifty elements in the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration; a few of those elements are shown in the following list:</span></span>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 <span data-ttu-id="2ef3e-110">Die folgende Abbildung zeigt die gefüllte Ellipse.</span><span class="sxs-lookup"><span data-stu-id="2ef3e-110">The following illustration shows the filled ellipse.</span></span>  
  
  <span data-ttu-id="2ef3e-111">![Screenshot, der zeigt, wie eine Ellipse mit einem Schraffurmuster aussieht.](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")</span><span class="sxs-lookup"><span data-stu-id="2ef3e-111">![Screenshot of what an ellipse filled with a hatch pattern looks like.](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")</span></span>
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2ef3e-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2ef3e-112">Compiling the Code</span></span>  
 <span data-ttu-id="2ef3e-113">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="2ef3e-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ef3e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ef3e-114">See also</span></span>

- [<span data-ttu-id="2ef3e-115">Verwenden eines Pinsels zum Ausfüllen von Formen</span><span class="sxs-lookup"><span data-stu-id="2ef3e-115">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
