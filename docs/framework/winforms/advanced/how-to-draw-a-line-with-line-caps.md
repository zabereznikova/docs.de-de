---
title: 'Vorgehensweise: Zeichnen einer Linie mit Linienenden'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
ms.openlocfilehash: a0d4d92d7201c4ac09eadd11d8f2e38a3c80c287
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713134"
---
# <a name="how-to-draw-a-line-with-line-caps"></a><span data-ttu-id="d59c9-102">Vorgehensweise: Zeichnen einer Linie mit Linienenden</span><span class="sxs-lookup"><span data-stu-id="d59c9-102">How to: Draw a Line with Line Caps</span></span>
<span data-ttu-id="d59c9-103">Sie können den Anfang oder Ende einer Zeile in einer von mehreren Formen namens Linienenden zeichnen.</span><span class="sxs-lookup"><span data-stu-id="d59c9-103">You can draw the start or end of a line in one of several shapes called line caps.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="d59c9-104">unterstützt verschiedene Linienenden, z. B. Roundrobin, Quadrat, Raute und Pfeilspitze.</span><span class="sxs-lookup"><span data-stu-id="d59c9-104">supports several line caps, such as round, square, diamond, and arrowhead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d59c9-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d59c9-105">Example</span></span>  
 <span data-ttu-id="d59c9-106">Sie können die Linienenden für den Anfang einer Linie (, StartCap), die das Ende einer Zeile (EndCap) oder die Striche eine gestrichelte Linie (DashCap) angeben.</span><span class="sxs-lookup"><span data-stu-id="d59c9-106">You can specify line caps for the start of a line (start cap), the end of a line (end cap), or the dashes of a dashed line (dash cap).</span></span>  
  
 <span data-ttu-id="d59c9-107">Im folgende Beispiel zeichnet eine Linie mit einer Pfeilspitze an einem Ende und einem runden Ende am anderen Ende.</span><span class="sxs-lookup"><span data-stu-id="d59c9-107">The following example draws a line with an arrowhead at one end and a round cap at the other end.</span></span> <span data-ttu-id="d59c9-108">Die Abbildung zeigt die resultierenden Zeile:</span><span class="sxs-lookup"><span data-stu-id="d59c9-108">The illustration shows the resulting line:</span></span>  
  
 <span data-ttu-id="d59c9-109">![Stifte](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")</span><span class="sxs-lookup"><span data-stu-id="d59c9-109">![Pens](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d59c9-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d59c9-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="d59c9-111">Erstellen Sie ein Windows Form und behandeln Sie das <xref:System.Windows.Forms.Control.Paint> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="d59c9-111">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="d59c9-112">Fügen Sie den Beispielcode in die <xref:System.Windows.Forms.Control.Paint> -Ereignishandler übergeben `e` als <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="d59c9-112">Paste the example code into the <xref:System.Windows.Forms.Control.Paint> event handler passing `e` as <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d59c9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d59c9-113">See also</span></span>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>
- [<span data-ttu-id="d59c9-114">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d59c9-114">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="d59c9-115">Verwenden eines Stifts zum Zeichnen von Linien und Formen</span><span class="sxs-lookup"><span data-stu-id="d59c9-115">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
