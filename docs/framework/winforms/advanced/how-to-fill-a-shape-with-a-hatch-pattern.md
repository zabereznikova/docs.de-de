---
title: 'Vorgehensweise: Ausfüllen einer Form mit einer Schraffur'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: 885f0d22e83767bda3ef76c54f0857dd2a148344
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719714"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a><span data-ttu-id="5512a-102">Vorgehensweise: Ausfüllen einer Form mit einer Schraffur</span><span class="sxs-lookup"><span data-stu-id="5512a-102">How to: Fill a Shape with a Hatch Pattern</span></span>
<span data-ttu-id="5512a-103">Eine Schraffur besteht aus zwei Farben: eine für den Hintergrund und eine für die Zeilen, die über dem Hintergrund der Muster bilden.</span><span class="sxs-lookup"><span data-stu-id="5512a-103">A hatch pattern is made from two colors: one for the background and one for the lines that form the pattern over the background.</span></span> <span data-ttu-id="5512a-104">Um eine geschlossene Form mit einer Schraffur zu füllen, verwenden eine <xref:System.Drawing.Drawing2D.HatchBrush> Objekt.</span><span class="sxs-lookup"><span data-stu-id="5512a-104">To fill a closed shape with a hatch pattern, use a <xref:System.Drawing.Drawing2D.HatchBrush> object.</span></span> <span data-ttu-id="5512a-105">Im folgenden Beispiel wird veranschaulicht, wie eine Ellipse mit einer Schraffur füllen:</span><span class="sxs-lookup"><span data-stu-id="5512a-105">The following example demonstrates how to fill an ellipse with a hatch pattern:</span></span>  
  
## <a name="example"></a><span data-ttu-id="5512a-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5512a-106">Example</span></span>  
 <span data-ttu-id="5512a-107">Die <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> Konstruktor akzeptiert drei Argumente: die Schraffurart, die Farbe der Schraffurlinie und die Farbe des Hintergrunds.</span><span class="sxs-lookup"><span data-stu-id="5512a-107">The <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor takes three arguments: the hatch style, the color of the hatch line, and the color of the background.</span></span> <span data-ttu-id="5512a-108">Das Schraffurstilargument möglich einen beliebigen Wert aus der <xref:System.Drawing.Drawing2D.HatchStyle> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="5512a-108">The hatch style argument can be any value from the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration.</span></span> <span data-ttu-id="5512a-109">Es gibt mehr als 50 Elemente in der <xref:System.Drawing.Drawing2D.HatchStyle> Enumeration; einige davon Elemente sind in der folgenden Liste dargestellt:</span><span class="sxs-lookup"><span data-stu-id="5512a-109">There are more than fifty elements in the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration; a few of those elements are shown in the following list:</span></span>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 <span data-ttu-id="5512a-110">Die folgende Abbildung zeigt die ausgefüllte Ellipse.</span><span class="sxs-lookup"><span data-stu-id="5512a-110">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="5512a-111">![Muster Schraffieren](./media/hatch1.png "hatch1")</span><span class="sxs-lookup"><span data-stu-id="5512a-111">![Hatch Pattern](./media/hatch1.png "hatch1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5512a-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="5512a-112">Compiling the Code</span></span>  
 <span data-ttu-id="5512a-113">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="5512a-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5512a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5512a-114">See also</span></span>
- [<span data-ttu-id="5512a-115">Verwenden eines Pinsels zum Ausfüllen von Formen</span><span class="sxs-lookup"><span data-stu-id="5512a-115">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
