---
title: "Gewusst wie: Verknüpfen von Linien"
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
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d12cc7b4b4c878ec812190fd56a1face64118ab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-join-lines"></a><span data-ttu-id="53310-102">Gewusst wie: Verknüpfen von Linien</span><span class="sxs-lookup"><span data-stu-id="53310-102">How to: Join Lines</span></span>
<span data-ttu-id="53310-103">Ein Join Zeile ist der allgemeinen Bereich, der zwei Zeilen gebildet wird, deren Enden erfüllen oder sich überlappen.</span><span class="sxs-lookup"><span data-stu-id="53310-103">A line join is the common area that is formed by two lines whose ends meet or overlap.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="53310-104">bietet drei Linienarten Join: Linienverbindungsstile, abschrägungen und gerundet wird.</span><span class="sxs-lookup"><span data-stu-id="53310-104"> provides three line join styles: miter, bevel, and round.</span></span> <span data-ttu-id="53310-105">Linienverbindungsstil ist eine Eigenschaft der <xref:System.Drawing.Pen> Klasse.</span><span class="sxs-lookup"><span data-stu-id="53310-105">Line join style is a property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="53310-106">Wenn Sie einen Linienverbindungsstil für eine <xref:System.Drawing.Pen> -Objekt, dass auf alle miteinander verbundenen Linien in einem Linienverbindungsstil angewendet werden <xref:System.Drawing.Drawing2D.GraphicsPath> Objekt mit diesem Stift gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="53310-106">When you specify a line join style for a <xref:System.Drawing.Pen> object, that join style will be applied to all the connected lines in any <xref:System.Drawing.Drawing2D.GraphicsPath> object drawn using that pen.</span></span>  
  
 <span data-ttu-id="53310-107">Die folgende Abbildung zeigt die Ergebnisse des Beispiels Join abgeschrägte Zeile.</span><span class="sxs-lookup"><span data-stu-id="53310-107">The following illustration shows the results of the beveled line join example.</span></span>  
  
 <span data-ttu-id="53310-108">![Stifte](../../../../docs/framework/winforms/advanced/media/pens5.gif "pens5")</span><span class="sxs-lookup"><span data-stu-id="53310-108">![Pens](../../../../docs/framework/winforms/advanced/media/pens5.gif "pens5")</span></span>  
  
## <a name="example"></a><span data-ttu-id="53310-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53310-109">Example</span></span>  
 <span data-ttu-id="53310-110">Sie können die Linienverbindungsstil angeben, mit der <xref:System.Drawing.Pen.LineJoin%2A> Eigenschaft von der <xref:System.Drawing.Pen> Klasse.</span><span class="sxs-lookup"><span data-stu-id="53310-110">You can specify the line join style by using the <xref:System.Drawing.Pen.LineJoin%2A> property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="53310-111">Das Beispiel zeigt einen Join abgeschrägte Zeile zwischen einer horizontalen Linie und eine vertikale Linie.</span><span class="sxs-lookup"><span data-stu-id="53310-111">The example demonstrates a beveled line join between a horizontal line and a vertical line.</span></span> <span data-ttu-id="53310-112">Im folgenden Code wird der Wert <xref:System.Drawing.Drawing2D.LineJoin.Bevel> zugewiesene der <xref:System.Drawing.Pen.LineJoin%2A> Eigenschaft ist ein Mitglied der <xref:System.Drawing.Drawing2D.LineJoin> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="53310-112">In the following code, the value <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assigned to the <xref:System.Drawing.Pen.LineJoin%2A> property is a member of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration.</span></span> <span data-ttu-id="53310-113">Die anderen Member der der <xref:System.Drawing.Drawing2D.LineJoin> Enumeration sind <xref:System.Drawing.Drawing2D.LineJoin.Miter> und <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span><span class="sxs-lookup"><span data-stu-id="53310-113">The other members of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration are <xref:System.Drawing.Drawing2D.LineJoin.Miter> and <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="53310-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="53310-114">Compiling the Code</span></span>  
 <span data-ttu-id="53310-115">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="53310-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53310-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53310-116">See Also</span></span>  
 [<span data-ttu-id="53310-117">Verwenden eines Stifts zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="53310-117">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
