---
title: "Gewusst wie: Ausfüllen einer Form mit einer Schraffur"
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
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f44289b79812f2330639cc333727bd21b6ef4fe6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a><span data-ttu-id="57448-102">Gewusst wie: Ausfüllen einer Form mit einer Schraffur</span><span class="sxs-lookup"><span data-stu-id="57448-102">How to: Fill a Shape with a Hatch Pattern</span></span>
<span data-ttu-id="57448-103">Eine Schraffur besteht aus zwei Farben: eine für den Hintergrund und eine für die Zeilen, die das Muster über dem Hintergrund bilden.</span><span class="sxs-lookup"><span data-stu-id="57448-103">A hatch pattern is made from two colors: one for the background and one for the lines that form the pattern over the background.</span></span> <span data-ttu-id="57448-104">Um eine geschlossene Form mit einer Schraffur zu füllen, verwenden Sie eine <xref:System.Drawing.Drawing2D.HatchBrush> Objekt.</span><span class="sxs-lookup"><span data-stu-id="57448-104">To fill a closed shape with a hatch pattern, use a <xref:System.Drawing.Drawing2D.HatchBrush> object.</span></span> <span data-ttu-id="57448-105">Im folgenden Beispiel wird veranschaulicht, wie eine Ellipse, die mit einer Schraffur füllen:</span><span class="sxs-lookup"><span data-stu-id="57448-105">The following example demonstrates how to fill an ellipse with a hatch pattern:</span></span>  
  
## <a name="example"></a><span data-ttu-id="57448-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="57448-106">Example</span></span>  
 <span data-ttu-id="57448-107">Die <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> Konstruktor hat drei Argumente: die Schraffurart, die Farbe der Schraffurlinie und die Farbe des Hintergrunds.</span><span class="sxs-lookup"><span data-stu-id="57448-107">The <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor takes three arguments: the hatch style, the color of the hatch line, and the color of the background.</span></span> <span data-ttu-id="57448-108">Das Schraffurstilargument kann einen beliebigen Wert zwischen der <xref:System.Drawing.Drawing2D.HatchStyle> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="57448-108">The hatch style argument can be any value from the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration.</span></span> <span data-ttu-id="57448-109">Es gibt mehr als 50 Elemente in der <xref:System.Drawing.Drawing2D.HatchStyle> -Enumeration; nur einige dieser Elemente sind in der folgenden Liste dargestellt:</span><span class="sxs-lookup"><span data-stu-id="57448-109">There are more than fifty elements in the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration; a few of those elements are shown in the following list:</span></span>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 <span data-ttu-id="57448-110">Die folgende Abbildung zeigt das ausgefüllte Ellipse.</span><span class="sxs-lookup"><span data-stu-id="57448-110">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="57448-111">![Muster Schraffieren](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")</span><span class="sxs-lookup"><span data-stu-id="57448-111">![Hatch Pattern](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="57448-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="57448-112">Compiling the Code</span></span>  
 <span data-ttu-id="57448-113">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="57448-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57448-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57448-114">See Also</span></span>  
 [<span data-ttu-id="57448-115">Verwenden eines Pinsels zum Ausfüllen von Formen</span><span class="sxs-lookup"><span data-stu-id="57448-115">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
